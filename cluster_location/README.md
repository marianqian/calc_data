Each output image has .RAW and .PNG file. 

`cluster_location_v1`: Contains the (20 mm, 50 calcs) large cluster and (10 mm, 50 calcs) small clusters. There are 5 phantoms where the individual calcification location is different, and the images are labelled with 0, 1, 2, 3, or 5. 

`cluster_location_v2`: Contains the (10 mm, 30 calcs) left cluster and (10 mm, 40 calcs) right cluster. There are 5 phantoms where the individual calcification location is different, and the images are labelled with 0, 1, 2, 3, or 5. 


## (Cluster Location](https://github.com/marianqian/cluster_generation_data/blob/master/README.md#cluster-location)
### Description
Changed the cluster location to either near the chest wall or to the nipple. Tested with 4 different configurations of cluster size and calc number: (10 mm, 50 calcs), (10 mm, 40 calcs), (10 mm, 30 calcs), (20 mm, 50 calcs). Below shows the configuration of the clusters, and the averages were across 4 values. Images located [here](https://github.com/marianqian/cluster_generation_data/tree/master/cluster_location). 
### Specifications
1. Calc size: varied between 3-9 voxels (mixed) 
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 
### Data
Image from `cluster_location_v1`, contains the (20 mm, 50 calcs) large cluster and (10 mm, 50 calcs) small clusters. 

![image](cluster_location/cluster_location_v1/prj_30mm_2_cluster_malignant_location_0_full_0.7_25.raw.gz.raw.png)

Image from `cluster_location_v2`, contains the (10 mm, 30 calcs) left cluster and (10 mm, 40 calcs) right cluster.

![image](cluster_location/cluster_location_v2/prj_30mm_2_cluster_malignant_location_2_0_full_0.7_25.raw.gz.raw.png)

### Results
![graph](cluster_location/graphs/cluster_location_graph_presentation.png)

| mm^3 (mixed)    | mean+std    |             |                    |
|-----------------|-------------|-------------|--------------------|
| Size of cluster | chest wall  | nipple      |     Mixed (3-9)    |
| 10 mm - 40      | 0.609±0.073 | 0.359±0.14  |     0.188±0.15     |
| 10 mm - 50      | 0.454±0.088 | 0.211±0.026 |     0.374±0.087    |
| 10 mm - 30      | 0.309±0.131 | 0.174±0.048 |     0.169±0.089    |
| 20 mm - 50      | 0.442±0.18  | 0.289±0.162 |     0.191±0.191    |

Clusters closer to the chest wall had a higher malignancy scores, surprisingly. Because clusters near the chest wall are not as common as clusters near the nipple, there might be other factors that contribute to its higher score. One potential reason could be that since the breast could be thicker near the chest wall, the clusters appear dimmer, which then could lead to a higher confidence score. Still not a confirmed conclusion, but because from other experiments we saw that dimmer clusters did have higher scores, this could be a possibility.
