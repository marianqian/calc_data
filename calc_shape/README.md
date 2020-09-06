Each output image has .RAW and .PNG file.

There are 5 phantoms where the individual calcification location is different, and the images are labelled with 0, 1, 2, 3, or 4. Each phantom has 3 rows (1st row for spherical, 2nd row for rod like, and 3rd row for both) and 4 columns (left to right: (20 mm, 50 calcs), (10 mm, 50 calcs), (10 mm, 40 calcs), (10 mm, 30 calcs)). 

## [Calcification Shape](https://github.com/marianqian/cluster_generation_data#calcification-shape)
### Description
Changed calcification shape to be rod-like instead of spherical. Tested with 4 configurations of cluster size and calc number: (20 mm, 50 calcs), (10 mm, 50 calcs), (10 mm, 40 calcs), (10 mm, 30 calcs). Each phantom contained three rows: 1st row for spherical, 2nd row for rod-like, and 3rd row for rod-like and spherical calcifications. The order of the clusters left to right are: (20 mm, 50 calcs), (10 mm, 50 calcs), (10 mm, 40 calcs), (10 mm, 30 calcs). The averages listed below are based off of 5 values. Images located [here](https://github.com/marianqian/cluster_generation_data/tree/master/calc_shape). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) 
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 
### Data

Image of clusters with different calcification shapes. From left to right: (20 mm, 50 calcs), (10 mm, 50 calcs), (10 mm, 40 calcs), (10 mm, 30 calcs). Rows: 1st is spherical, 2nd is rod-like, 3rd is both. 

![image](../calc_shape/prj_30mm_2_cluster_malignant_calc_shape_0_full_0.7_25.raw.gz.raw.png)

### Results
Mean and Standard Deviation. 
| mm^3 (mixed)    | mean+std    |             |             |
|-----------------|-------------|-------------|-------------|
| Size of cluster | spherical   | rod like    | both        |
| 10 mm - 30      | 0.289±0.183 | 0.518±0.09  | 0.381±0.1   |
| 10 mm - 40      | 0.479±0.074 | 0.389±0.176 | 0.272±0.048 |
| 10 mm - 50      | 0.443±0.093 | 0.5±0.077   | 0.349±0.161 |
| 20 mm - 50      | 0.519±0.124 | 0.23±0.14   | 0.471±0.208 |

Sometimes the spherical calcs have a higher score and other times the rod-like calcifications have a higher score. No definite conclusion about whether having rod-like clusters would increase malignancy scores. 

