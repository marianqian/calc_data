Each output image has a .RAW file and .PNG file.

Each phantom has one size of cluster in voxels (5 mm = 71 vx, 10 mm = 142 vx) and there are 12 clusters of 3 rows by 5 columns in each phantom. 

From the README.md
## [Modeling Non-Uniform Clusters](https://github.com/marianqian/cluster_generation_data#modeling-non-uniform-clusters)
### Description
Because the smaller sized calcifications showed an increase in confidence scores, we tried creating nonuniform clusters where 10% of the calcifications were sized 7-9 voxels. We found the confidence scores for 5 mm and 10 mm sized clusters with 40 calcs. There was one phantom for 12 clusters of 5 mm, and another phantom for 12 clusters of 10 mm. The averages computed here are across the 12 values. Images are located [here](https://github.com/marianqian/cluster_generation_data/tree/master/nonuniform_clusters). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) with 10% of calcifications being 7-9 voxels  
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data

10 mm sized cluster with 40 calcs. 

![image](nonuniform_cluster/graphs/10mm_40calcs_small_nonuniform.png)

5 mm sized cluster with 40 calcs. 

![image](nonuniform_cluster/graphs/5mm_40calcs_small_nonuniform.png)

### Results
![image](nonuniform_cluster/graphs/slide8_mixed_nonuniform_calcs_graph.png)

| 10 mm | col 1    | col 2       | col 3    | col 4    | 5 mm  | col 1    | col 2       | col 3    | col 4    |
|-------|----------|-------------|----------|----------|-------|----------|-------------|----------|----------|
| row 1 | 0.556733 | 0.543662    | 0.281778 | 0.653176 | row 1 | 0.101907 | 0.201929    | 0.214445 | 0.290343 |
| row 2 | 0.673025 | 0.495329    | 0.438144 | 0.595632 | row 2 | 0.217172 | 0.17257     | 0.174818 | 0.182554 |
| row 3 | 0.641574 | 0.520911    | 0.639943 | 0.548619 | row 3 | 0.181075 | 0.299382    | 0.149039 | 0.100873 |
|       | Mean     | 0.549±0.105 |          |          |       | Mean     | 0.191±0.059 |          |          |
