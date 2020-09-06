# calc_data
describe the different experiments and the timeline of their results 
most images for preprocessing, i used 


Slide 8 in presentation. 
Changing number of calcifications and size of cluster
Clusters with more calcifications  higher malignancy confidence score 
Clusters with size 10 mm3 compared to 20 mm3 and 5 mm3 size clusters  slightly higher scores

mixed calcs
| MIXED       | 10                | 20              | 30               | 40                | 50               |
|-------------|-------------------|-----------------|------------------|-------------------|------------------|
| 5 (71 vx)   | 0.171±0.104       | 0.419±0.103     | 0.429±0.068      | 0.464±0.089       | 0.498±0.072      |
| 10 (142 vx) | 0.21±0.183        | 0.232±0.156     | 0.467±0.146      | 0.572±0.123       | 0.624±0.179      |
| 20 (285 vx) | 0.071±0.042       | 0.275±0.174     | 0.189±0.103      | 0.431±0.152       | 0.407±0.191      |
| 20 (285 vx) | 0.019±0.032-0.018 | 0.125±0.08-0.08 | 0.11±0.202-0.108 | 0.229±0.126-0.126 | 0.266±0.06-0.247 |


small calcs
| SMALL       | 10                | 20              | 30               | 40                | 50               |
|-------------|-------------------|-----------------|------------------|-------------------|------------------|
| 5 (71 vx)   | 0.084±0.05        | 0.117±0.051     | 0.104±0.062      | 0.122±0.053       | 0.085±0.032      |
| 10 (142 vx) | 0.184±0.125       | 0.344±0.135     | 0.402±0.122      | 0.451±0.089       | 0.516±0.096      |
| 20 (285 vx) | 0.119±0.103       | 0.14±0.117      | 0.236±0.149      | 0.143±0.082       | 0.354±0.166      |
| 20 (285 vx) | 0.019±0.032-0.018 | 0.125±0.08-0.08 | 0.11±0.202-0.108 | 0.229±0.126-0.126 | 0.266±0.06-0.247 |


mean ± TOP std   - BOTTOM std
| mm^3            |  |                   |                   |                   |                   |
|-----------------|-------------------------------|-------------------|-------------------|-------------------|-------------------|
| Size of cluster | 10                            | 20                | 30                | 40                | 50                |
| 5 (71 vx)       | 0.094±0.099-0.094             | 0.114±0.096-0.096 | 0.091±0.021-0.021 | 0.081±0.045-0.045 | 0.079±0.02-0.02   |
| 10 (142 vx)     | 0.105±0.143-0.104             | 0.247±0.202-0.202 | 0.255±0.135-0.135 | 0.331±0.133-0.133 | 0.382±0.088-0.088 |
| 20 (285 vx)     | 0.019±0.032-0.018             | 0.125±0.08-0.08   | 0.11±0.202-0.108  | 0.229±0.126-0.126 | 0.266±0.06-0.247  |


| mm^3            | Num calcs   |             |             |             |                                                                        |
| --------------- | ----------- | ----------- | ----------- | ----------- | ---------------------------------------------------------------------- |
| Size of cluster | 10          | 20          | 30          | 40          | 50                                                                     |
| 5 (71 vx)       | 0.056887127 | 0.104886264 | 0.07405398  | 0.099108025 | 0.096362464                                                            |
| 10 (142 vx)     | 0.05602796  | 0.468650311 | 0.308111638 | 0.257900625 | 0.393199652                                                            |
| 20 (285 vx)     | 0           | 0.088635035 | 0           | 0.362236261 | 0.692064523697 (not counted in graph as outier)                        |
| 1               |             |             |             |             |                                                                        |
| 5 (71 vx)       | 0.018788677 | 0.106407657 | 0.116770208 | 0.053639639 | 0.099187247                                                            |
| 10 (142 vx)     | 0.039953906 | 0.065078937 | 0.205674797 | 0.486473322 | 0.333029389                                                            |
| 20 (285 vx)     | 0           | 0.236876726 | 0.40355742  | 0.273835123 | 0.244947866                                                            |
| 2               |             |             |             |             |                                                                        |
| 5 (71 vx)       | 0.216874242 | 0.090277083 | 0.081755765 | 0.036008392 | 0.073067717                                                            |
| 10 (142 vx)     | 0.096151851 | 0.129232824 | 0.393985778 | 0.251083136 | 0.441211224                                                            |
| 20 (285 vx)     | 0.063525707 | 0.138343737 | 0.146863222 | 0.143113181 | 0.301585078                                                            |
| 3               |             |             |             |             |                                                                        |
| 5 (71 vx)       | 0.075171351 | 0.037759751 | 0.07948292  | 0.091788918 | 0.05914256                                                             |
| 10 (142 vx)     | 0.023329563 | 0.308634728 | 0.124841258 | 0.220704779 | 0.459721148                                                            |
| 20 (285 vx)     | 0           | 0.076781414 | 0           | 0.254817128 | 0.318397105                                                            |
| 4               |             |             |             |             |                                                                        |
| 5 (71 vx)       | 0.102960855 | 0.230610937 | 0.102871142 | 0.12666449  | 0.067681476                                                            |
| 10 (142 vx)     | 0.309486151 | 0.261789501 | 0.243857563 | 0.440784574 | 0.284140795                                                            |
| 20 (285 vx)     | 0.029512633 | 0.08436054  | 0           | 0.110592023 | 0.198714361                                                            |

7. results num calcs 
for our results, the first parametres we changed were the number of calcs and size of the cluster. we found that clusters with more calcs had a higher confidence score, as seen in the graph on the right where the confidence scores show an upward trend as the number of calcs also increase. another observation we saw was that the clusters with size 10 mm^3 had slightly higher scores as well which is indicated by the orange data points. 

8. results location 
we also tried changing the location of the cluster, and surprisingly saw that clusters closer to the chest wall had a higher confidence score as shown by the blue bars. 

because clusters near the chest wall are not as common as clusters near the nipple, we thought that there might be other factors that contributed to its higher score, one of them being that since the breast could be thicker near the chest wall, the clusters appear dimmer which could then lead to a higher confidence score. because of that, we still plan  to explore further before coming to a conclusion. 

9. results size of calc
we also varied the size of the calcifications, mainly testing the difference between small, large, and mixed sizes. we saw that smaller calcifications had increased confidence scores for 5 and 10 mm cubed sized clusters, and the only scores for the 10 mm sized clusters are shown in the bar graph for clarity. the blue represents the confidence scores of the smaller calcs. 

one reason that could be behind why the smaller sized calcs had a higher confidence score is how bright it shows up in the simulated image as the larger calcs show up alot brighter which then could be unrealistic to the cad algorithm. 

10. results density 
we tested whether brightness had an impact on the confidence scores by changning the density of the invidual calcifications. the density values we tested were from 1.5 to 2 grams per cm cubed and a lower density resulted in calcs not showing up as bright. the lower densities did in fact have a higher malignancy score for mixed clusters as well, and the orange data points are the mean confidence score values of the density settings. 

11. discussion 
this leads to our experiments leaning towards how calficaitons that are too bright could lead to decrease in confidence scores because they are too unrealisitc, and this was shown through changing the density settings in MCGPU and increasing the size of calcifications. this could also explain why the smaller calcs ahd higher scores. increasing the number of calcifications however did increase the confidence scores. we plan to experiment with the linear shape of the clusters and place calcification clusters near simulated masses as the next steps to see whether these factors also influence the malignancy confidence scores.


