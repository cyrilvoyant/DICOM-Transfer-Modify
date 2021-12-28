# DICOM-Transfer-Modify
Dicom Tool using dcmdjpeg dcmmodify gdmconv storescu
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% To do only once%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


To use the scripts of the "code.bat" batch, you must have dl and installed the DCMTK suite
from the offis group (https://dicom.offis.de/dcmtk.php.en) and the GDCM suite.


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% To do when necessary%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

-Only do this methodology if the usual dicom transfer software (e.g. CD2RTP for adac pinnacle) software does not work

-Place the images in the IMAGES directory

-Check if they all have the same weight
  -if YES: they are probably in "Little Endian" format compatible with ADAC-Pinnacle
  -if NO: they are compressed (JPEG format) and not compatible with ADAC-Pinnacle

-To ensure the compression, open for exemple ezDicom then pull in the window that opens an image which is contained in the IMAGES directory

- Show DICOM tags and watch (00002,0010) if the end is 1.2.1 then there is no compression, otherwise they are certainly compressed

-Open the batch code.bat by doing a RIGHT_CLICK / Modify, the code allows you to perform 4 actions:
  -add a .dcm extension to the images contained in IMAGES
  -decompress these images (normal JPEG or JP2000)
  -modify their DICOM characteristics
  -export these images in Pinnacle

-To deselect the actions to be executed, add "rem" at the beginning of the line in the script
