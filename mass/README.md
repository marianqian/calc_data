* CAD_inserted_mass_1.06_mcgpu_fredenberg.png - CAD output of the processed image
* inserted_mass_1.06_mcgpu_fredenberg.png - processed image using default values and 1.06 density
* inserted_mass_1.06_mcgpu_fredenberg.raw - processed image .RAW file using default values and 1.06 density
* inserted_mass_1.06_mcgpu_fredenberg_mcgpu_output.gz - **not** processed image straight from MCGPU simulation, 1.06 density


## [Mass](https://github.com/marianqian/cluster_generation_data#mass)
### Description
For CAD algorithm, tested simulated spiculated masses created by Nick Neirotti. Simulated using fredenberg mass material file. Images located [here](https://github.com/marianqian/cluster_generation_data/tree/master/mass). 
### Specifications
1. Density in MC-GPU simulation: 1.06
2. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data
Simulated processed image.

![image](../mass/inserted_mass_1.6_mcgpu_fredenberg.png) 

CAD output 

![image](../mass/CAD_inserted_mass_1.6_mcgpu_fredenberg.png) 

The highest two lesions had very noticable spiculations. and the highest scoring mass was slightly deformed/irregularly shaped. This could lead to how having lesions that are not perfectly spheres could possibly increase the malignancy confidence score. 

## Future steps
For masses to see influence on confidence score:
* Place masses in same location but in different phantoms.
* Place masses in uniform phantom.
* Populate phantom with perfect sphere masses.
* Take masses and replicate them across a phantom so the only difference is the location. 
