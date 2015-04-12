# Registration

[Official documentation](http://www.itk.org/Doxygen/html/RegistrationPage.html)

#### Registration is decomposed into:

- **target**  
  object that will stay static
- **reference**  
  object that will be transformed to be mapped to **target**
- **transform**  
  mapping that will convert **reference** to match **target**
- **metric**  
  'precision' of mapping
- **mapper**  
  technique that will interpolate values when objects are resampled through transform
- **optimizer**  
  finds **transform** parameters which will optimize **metric**
  
#### Transforms
- affine  
- rigid3D  
- rigid3Dperspective  
- translation  
- spline

#### Metrics
- mean squares  
- mormalized correlation  
- pattern intensity  
- mutual information  

#### Optimizers
- gradient descent  
- regular step gradient descent  
- conjugate gradient  
- levenberg marquardt  
- LBFGS  
- amoeba  
- one plus one evolutionary  

