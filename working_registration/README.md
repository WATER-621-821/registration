# HOW TO RUN

You have to have the following hierarchy:

    registration.exe
    f/
    |
    `-+-- fixedImage1.dcm
      |
      +-- fixedImage2.dcm
      | 
      +- ...
      |
      +-- fixedImageN.dcm
    m/
    |
    `-+-- movingImage1.dcm
      |
      +-- movingImage2.dcm
      | 
      +- ...
      |
      +-- movingImageN.dcm
    out1/<empty>
    out2/<empty>
    
Put images into f/ (stands for fixed) and m/ (stands for moving).
Then run

    DeformableRegistration16.exe f m out1 out2
    
Registered images will appear in out1.
Registration will take around 3-4 hours. 
