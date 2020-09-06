### Description
### Specifications
### Data
### Results

# Results of Modeling Malignant and Benign Clusters 
## Changing Size of Calcification and Size of Cluster (Version 2) 

### Description
(slide 8 in presentation) 
Experimented with varying size of cluster for 5 mm (71 voxels), 10 mm (142 voxels), and 20 mm (285 voxels). Calcifications varied from 10 to 50 in increments of 10. For 5 and 10 mm, each phantom had 3 rows by 4 columns of clusters, and for 20 mm, each phantom had 3 rows by 3 columns. We ran this experiment twice, once with mixed sized calcs (3-9 voxels) and small sized calcs (3-5 voxels). Images are located [here](https://github.com/marianqian/cluster_generation_data/tree/master/num_calcs_size_cluster/num_calcs_size_cluster_v2).

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) and 3-5 voxels (small) 
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data
#### Mixed 
The image below is of an example 10 mm with 40 mixed sized calcification clusters. 

![example_image](num_calcs_size_cluster/graphs/10mm_40calcs_mixed_updated.png)

#### Small
We also ran the same exact experiment but with **small** calcifications where the calcifications ranged from 3 to 5 voxels. Here is an image of 10 mm with 40 small sized calcification clusters. 

![example_image](num_calcs_size_cluster/graphs/10mm_40calcs_small.png)

### Results
#### Mixed

| MIXED (3-9) | 10                | 20              | 30               | 40                | 50               |
|-------------|-------------------|-----------------|------------------|-------------------|------------------|
| 5 (71 vx)   | 0.171±0.104       | 0.419±0.103     | 0.429±0.068      | 0.464±0.089       | 0.498±0.072      |
| 10 (142 vx) | 0.21±0.183        | 0.232±0.156     | 0.467±0.146      | 0.572±0.123       | 0.624±0.179      |
| 20 (285 vx) | 0.071±0.042       | 0.275±0.174     | 0.189±0.103      | 0.431±0.152       | 0.407±0.191      |

![](num_calcs_size_cluster/graphs/slide8_mixed_calcs_graph.png)

#### Small
| SMALL (3-5) | 10                | 20              | 30               | 40                | 50               |
|-------------|-------------------|-----------------|------------------|-------------------|------------------|
| 5 (71 vx)   | 0.084±0.05        | 0.117±0.051     | 0.104±0.062      | 0.122±0.053       | 0.085±0.032      |
| 10 (142 vx) | 0.184±0.125       | 0.344±0.135     | 0.402±0.122      | 0.451±0.089       | 0.516±0.096      |
| 20 (285 vx) | 0.119±0.103       | 0.14±0.117      | 0.236±0.149      | 0.143±0.082       | 0.354±0.166      |

![](num_calcs_size_cluster/graphs/slide8_small_calcs_graph.png)

Most averages had 12 values, but for most of the 20 mm sized clusters, the CAD algorithm didn't detect 3-5 of the clusters. The highest values were with small calcs/10 mm/50 calcs. From the graph, it looks like the 5 mm with small calcs had higher confidence scores compared to the 5 mm mixed calcs consistently as well. The lowest scores were from mixed calcs/5 mm/10 calcs and small calcs/20 mm/10 calcs (for this one the CAD algorithm had a hard time detecting the clusters as well.) 

Clusters with more calcifications had a higher malignancy confidence score where the confidence scores show an upward trend as the number of calcs increase for 5 and 10 mm sized clusters. 10 mm sized clusters also had higher scores compared to the other sizes (orange points). The clusters with smaller calcifications had a noticeable increase in malignancy scores.

## Changing Size of Calcification and Size of Cluster (Version 1) OLD
### Description
Experimented with varying size of cluster for 5 mm (71 voxels), 10 mm (142 voxels), and 20 mm (285 voxels). Calcifications varied from 10 to 50 in increments of 10. For the data points, each phantom had 5 clusters with each cluster having a different number of calcifications with the same cluster size. There were phantoms for each cluster size. Images are located [here](https://github.com/marianqian/cluster_generation_data/tree/master/num_calcs_size_cluster/num_calcs_size_cluster_v1). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) 
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data
Image of 10 mm sized cluster. 

![](num_calcs_size_cluster/num_calcs_size_cluster_v1/prj_30mm_2_cluster_malignant_10mm_1_full_0.7_25.raw.gz.raw.png)
### Results
![](num_calcs_size_cluster/graphs/slide8_mixed_calcs_graph_presentation.png)

| mm^3            |  |                   |                   |                   |                   |
|-----------------|-------------------------------|-------------------|-------------------|-------------------|-------------------|
| Size of cluster | 10                            | 20                | 30                | 40                | 50                |
| 5 (71 vx)       | 0.094±0.099-0.094             | 0.114±0.096-0.096 | 0.091±0.021-0.021 | 0.081±0.045-0.045 | 0.079±0.02-0.02   |
| 10 (142 vx)     | 0.105±0.143-0.104             | 0.247±0.202-0.202 | 0.255±0.135-0.135 | 0.331±0.133-0.133 | 0.382±0.088-0.088 |
| 20 (285 vx)     | 0.019±0.032-0.018             | 0.125±0.08-0.08   | 0.11±0.202-0.108  | 0.229±0.126-0.126 | 0.266±0.06-0.247  |

Each mean was across 5 values. The error bars were **not** standard deviation, but was the average of the maximum and minimum values. The 10 mm clusters also showed higher scores than the other sizes, and we saw a higher number of calcifications led to a higher malignancy score. 

## Modeling Non-Uniform Clusters
### Description
Because the smaller sized calcifications showed an increase in confidence scores, we tried creating nonuniform clusters where 10% of the calcifications were sized 7-9 voxels. We found the confidence scores for 5 mm and 10 mm sized clusters with 40 calcs. There was one phantom for 12 clusters of 5 mm, and another phantom for 12 clusters of 10 mm. The averages computed here are across the 12 values. Images are located [here](https://github.com/marianqian/cluster_generation_data/tree/master/nonuniform_clusters). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed) with 10% of calcifications being 7-9 voxels  
2. Density in MC-GPU simulation: 1.6
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Data

10 mm sized cluster with 40 calcs. 

![](nonuniform_cluster/graphs/10mm_40calcs_small_nonuniform.png)

5 mm sized cluster with 40 calcs. 

![](nonuniform_cluster/graphs/5mm_40calcs_small_nonuniform.png)

### Results
![](nonuniform_cluster/graphs/slide8_mixed_nonuniform_calcs_graph.png)

| 10 mm | col 1    | col 2       | col 3    | col 4    | 5 mm  | col 1    | col 2       | col 3    | col 4    |
|-------|----------|-------------|----------|----------|-------|----------|-------------|----------|----------|
| row 1 | 0.556733 | 0.543662    | 0.281778 | 0.653176 | row 1 | 0.101907 | 0.201929    | 0.214445 | 0.290343 |
| row 2 | 0.673025 | 0.495329    | 0.438144 | 0.595632 | row 2 | 0.217172 | 0.17257     | 0.174818 | 0.182554 |
| row 3 | 0.641574 | 0.520911    | 0.639943 | 0.548619 | row 3 | 0.181075 | 0.299382    | 0.149039 | 0.100873 |
|       | Mean     | 0.549±0.105 |          |          |       | Mean     | 0.191±0.059 |          |          |

# Experiments focusing on brightness of the calcification (location, density, calcification size)

We saw through our experiments that calcifications that were too bright would lead to a decrease in confidence scores possibly because they are too unrealistic. This was shown through changing the density settings in MC-GPU (lower densities had higher scores) and increasing the size of calcifications (smaller calc sizes had higher scores). Clusters near the chest wall also had higher scores which could be due to change in brightness (discussed more in detail below). 

## Calcification Density (version 2)
### Description
Experimented with the density setting in MC-GPU to see whether the brightness had an impact on the confidence score. The density values we tested were from 1.5 to 2.0 g/cm^3, and a lower density results in a dimmer image where the calcifications do not show up as bright. We used 10 different phantoms with 5 clusters placed in the same location (along the middle of the breast), but the individual calcification locations were different. The clusters were of 10 mm sized and 40 calcifications. The averages were based on 10 values in the same column across the 10 different breast phantoms. Images located [here](https://github.com/marianqian/cluster_generation_data/tree/master/calc_density/calc_density_v2). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed)   
2. Density in MC-GPU simulation: 1.5-2.0 (varied)
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Results
![image](calc_density/calc_density_graphs.png)

|     | col 1       | col 2       | col 3       | col 4       | col 5       |
|-----|-------------|-------------|-------------|-------------|-------------|
| 1.5 | 0.429±0.085 | 0.418±0.063 | 0.455±0.086 | 0.429±0.148 | 0.461±0.103 |
| 1.6 | 0.422±0.106 | 0.393±0.053 | 0.463±0.069 | 0.416±0.069 | 0.395±0.132 |
| 1.7 | 0.384±0.102 | 0.373±0.078 | 0.429±0.084 | 0.38±0.095  | 0.362±0.127 |
| 1.8 | 0.369±0.085 | 0.357±0.076 | 0.406±0.057 | 0.362±0.084 | 0.323±0.091 |
| 1.9 | 0.345±0.103 | 0.328±0.067 | 0.405±0.073 | 0.371±0.073 | 0.331±0.109 |
| 2   | 0.308±0.093 | 0.299±0.05  | 0.353±0.086 | 0.32±0.071  | 0.287±0.101 |

The graphs show a consistent trend for lower densities having higher confidence scores. The standard deviations for most of the values were around 0.1. 


## Calcification Density (version 3) tried some experiments 
### Description
We tried using another breast phantom made by Dr. Andrey Makeev of a uniform ellipsoid breast phantom with only two materials, 0 for air and 1 for adipose tissue. The phantom had 15 clusters, each 10 mm sized with 40 calcifications. Images with different density settings from 1.5 to 2.0 and the breast phantom can be found [here](https://github.com/marianqian/cluster_generation_data/tree/master/calc_density/calc_density_v3). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed)   
2. Density in MC-GPU simulation: 1.5-2.0 (varied)
3. Preprocessing: Had to manually process due to the new breast phantom 

## Data
Generated image output of 1.6 density. 15 clusters, 10 mm and 40 calcifications. 

![image](calc_density/ellip_calc_1.6.png)

Output of the CAD algorithm

![image](calc_density/ellip_calc_1.6_cad_output_all.png)

We decided to use this approach so that the background would be uniform, and that would reduce the variability between the clusters, which would hopefully allow for less variation in the confidence scores from the CAD algorithm. However, we did not proceed with this approach because the algorithm gave a large range of values for several clusters that visually looked similar. 

## Calcification Density (version 1) OLD
### Description
An older experiment testing changing the density in MC-GPU. The density values we tested were from 1.5 to 2.0 g/cm^3, and a lower density results in a dimmer image where the calcifications do not show up as bright. The phantom contained 5 clusters along the middle of the breast, and the averages were based on those 5 values. The same phantom was used for all the different density settings. Each cluster was 10 mm with 40 calcs, and we tested this with mixed (3-9 voxel) calcs and small (3-5 voxel) calcs. Images are located [here](https://github.com/marianqian/cluster_generation_data/tree/master/calc_density/calc_density_v1). 

### Specifications
1. Calc size: varied between 3-9 voxels (mixed), 3-5 voxels (small)   
2. Density in MC-GPU simulation: 1.5-2.0 (varied)
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 

### Results

Graph only shows values for the **mixed** clusters. 
![image](calc_density/calc_density_graphs_presentation.png)


|              Density   g/cm^3    |             1.5    |             1.6    |            1.7    |            1.8    |             1.9    |               2    |
|---------------------------------:|-------------------:|-------------------:|------------------:|------------------:|-------------------:|-------------------:|
|     10   mm - 40 calcs (mixed, 3-9)    |     0.498±0.056    |     0.421±0.074    |     0.397±0.09    |     0.406±0.09    |     0.365±0.067    |     0.347±0.082    |
| 10 mm - 40 calcs (small, 3-5) | 0.346±0.222 | 0.565±0.154 | 0.434±0.26 | 0.347±0.082 | 0.609±0.056 | 0.629±0.11 |

For the mixed calcs, lower density settings had higher malignancy scores. For the small clusters, they had higher scores for a higher density setting, which could possibly be because the lower settings did not allow the smaller calcs to show up bright enough. 


## Cluster Location
thought that could be due to 

we also tried changing the location of the cluster, and surprisingly saw that clusters closer to the chest wall had a higher confidence score as shown by the blue bars. 

because clusters near the chest wall are not as common as clusters near the nipple, we thought that there might be other factors that contributed to its higher score, one of them being that since the breast could be thicker near the chest wall, the clusters appear dimmer which could then lead to a higher confidence score. because of that, we still plan  to explore further before coming to a conclusion. 

### Description
### Specifications
1. Calc size: varied between 3-9 voxels (mixed) 
2. Density in MC-GPU simulation: 1.5-2.0 (varied)
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 
### Data
![image](cluster_location/cluster_location_v1/prj_30mm_2_cluster_malignant_location_0_full_0.7_25.raw.gz.raw.png)

### Results


## Calcification Size
we also varied the size of the calcifications, mainly testing the difference between small, large, and mixed sizes. we saw that smaller calcifications had increased confidence scores for 5 and 10 mm cubed sized clusters, and the only scores for the 10 mm sized clusters are shown in the bar graph for clarity. the blue represents the confidence scores of the smaller calcs. 

one reason that could be behind why the smaller sized calcs had a higher confidence score is how bright it shows up in the simulated image as the larger calcs show up alot brighter which then could be unrealistic to the cad algorithm. 

# not related
## Calcification Shape
## Linear Clusters
we plan to experiment with the linear shape of the clusters and place calcification clusters near simulated masses as the next steps to see whether these factors also influence the malignancy confidence scores.


## Mass

### Description
### Specifications
1. Calc size: varied between 3-9 voxels (mixed) 
2. Density in MC-GPU simulation: 1.5-2.0 (varied)
3. Preprocessing: Default values (25th to 100th percentile, masked 400,000, took values greater than 0.7) 
### Data
### Results




