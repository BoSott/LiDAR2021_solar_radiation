CloudCompare:
1. extract all but the the as "unclassfied" pre-defined class from the large_ds.las
2. compute 2.5D Mesh (best fitting plane) with 0 as max Mesh length -> no max value due to house sides (no visual difference to XY plane)
3. create point cloud with 10 points per squaremeter -> 33 Mio Points (quite some more points than more than before)
4. Clone the point cloud
5. Merge the cloned point cloud with the result of the tree "pre-classified" segmentation with this layer
