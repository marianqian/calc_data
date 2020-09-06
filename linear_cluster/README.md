Each output image has .RAW and .PNG file.

Separated into folders labelled with the different configurations described below. In each folder, there is one phantom for each of the following: (10 mm, 20 calcs), (10 mm, 30 calcs), (10 mm, 40 calcs), (10 mm, 50 calcs), (20 mm, 50 calcs). The label of each image has the cluster size (5mm = 71vx, 10 mm = 142 vx, 20 mm = 285 vx) and the number of calcifications. Inside each phantom has 12 clusters, 3 rows by 4 columns. 

## [Linear Clusters](https://github.com/marianqian/cluster_generation_data#linear-clusters)
### Description
Tested whether changing the cluster shape into a linear pattern would influence malignancy scores. Tried several different configurations listed below:  

* **(3-7_linear_15-30)** Linear cluster, 3-7 voxel sized calcs, calcs had to be min 15 and max 30 pixels away from the center line. 
* **(3-7_linear_15-30_same_cluster)** Linear cluster, 3-7 voxel sized calcs, calcs had to be min 15 and max 30 pixels away from the center line. **the same cluster with same calc locations was placed throughout the phantom**
* **(3-9_linear_0-15)** Linear cluster, 3-9 voxel sized calcs, calcs had to be min 0 and max 15 pixels away from the center line.
* **(3-9_linear_5-20)** Linear cluster, 3-9 voxel sized calcs, calcs had to be min 5 and max 20 pixels away from the center line. 
* **(3-9_linear_15-30)** Linear cluster, 3-9 voxel sized calcs, calcs had to be min 15 and max 30 pixels away from the center line. 
* **(3-7_random)** Random cluster, 3-7 voxel sized calcs
* **(3-9_random)** Random cluster, 3-9 voxel sized calcs

In each of these configurations, there were phantoms for the following: (10 mm, 20 calcs), (10 mm, 30 calcs), (10 mm, 40 calcs), (10 mm, 50 calcs), (20 mm, 50 calcs). Each phantom one configuration of 3 rows by 4 columns of clusters. The averages of each configuration was based on the 4 clusters in the middle row. Images located [here](https://github.com/marianqian/cluster_generation_data/tree/master/linear_cluster). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) and 3-7 voxels 
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data
Image of linear cluster of 10 mm and 20 calcs. The calcs were 3-7 voxel sized and had to be min 15 pixels and max 30 pixels away from the center line. 

![image](linear_cluster/3-7_linear_15-30/prj_30mm_2_linear_cluster_142_20nm_1_full_0.7_25.raw.gz.raw.png)

### Results

| mm^3            | mean+std         |                               |                 |                 |                  |              |              |
|-----------------|------------------|-------------------------------|-----------------|-----------------|------------------|--------------|--------------|
| Size of cluster | 3-7_linear_15-30 | 3-7_linear_15-30_same_cluster | 3-9_linear_0-15 | 3-9_linear_5-20 | 3-9_linear_15-30 | 3-7_random   | 3-9_random   |
| 10 mm - 20      | 0.367±0.065      | 0.391±0.065                   | 0.145±0.029     | 0.166±0.027     | 0.212±0.076      | 0.447±0.078  | 0.405±0.077  |
| 10 mm - 30      | 0.501±0.032      | 0.393±0.072                   | 0.124±0.045     | 0.188±0.038     | 0.253±0.057      | 0.509±0.068  | 0.374±0.058  |
| 10 mm - 40      | 0.518±0.082      | 0.455±0.054                   | 0.115±0.014     | 0.171±0.046     | 0.264±0.055      | 0.599±0.056  | 0.469±0.032  |
| 10 mm - 50      | 0.525±0.046      | 0.51±0.033                    | 0.059±0.019     | 0.18±0.055      | 0.371±0.06       | 0.734±0.023  | 0.545±0.036  |
| 20 mm - 50      | 0.499±0.127      | 0.481±0.125                   | 0.118±0.038     | 0.196±0.058     | 0.215±0.059      | Not enough data | Not enough data |

### Future Steps 
The linear clusters didn't have as high malignancy scores compared to the random clusters, but there was also variability in this experiment. Some future steps: 
1. Location of the linear cluster might impact the score
2. Make the linear clusters that are tightly clustered together and have more calcifications to be less bright. 
3. Make linear clusters longer and more sparsely distributed. 
4. Vary the length, number of calcifications, and how dense the linear cluster is to see how well the CAD algorithm performs. 
5. Preprocessing might make a difference (the ones for this experiment was with the default values). 
