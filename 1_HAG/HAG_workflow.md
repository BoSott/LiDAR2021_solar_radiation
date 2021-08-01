# DTM calculation:
2 meter cell size DTM:
1.	extract ground class 2 with CloudCompare -> Edit -> Scalar fields -> Filter by Value and save as .las
2.	opalsImport -inf large_ground_class_2.las -iformat las
3.	opalsCell -inf large_ground_class_2.odm -outf large_ground_class_2.tif -feature min -CellSize 2.0
4.	opalsStatFilter -inFile large_ground_class_2.tif -outFile large_dtm_2m_k5_smooth.tif -feature mean -kernelSize 5

10 meter cell size DTM:
1.	extract ground class 2 with CloudCompare -> Edit -> Scalar fields -> Filter by Value and save as .las
2.	opalsImport -inf large_ground_class_2.las -iformat las
3.	opalsCell -inf large_ground_class_2.odm -outf lare_ground_class2_10.tif -feature min -CellSize 10.0
4.	opalsStatFilter -inFile large_ground_class2_10.tif -outFile large_dtm_10m_k4_smooth.tif -feature mean -kernelSize 4

filling NoData Cells in the 2m DTM
1.	opalsAlgebra -inFile large_dtm_2m_k5_smooth.tif large_dtm_10m_k4_smooth.tif -outfile large_dtm_filled.tif -gridSize 2.0 -formula "return r[1] if ( r[0] is None) else r[0]"

OUTPUT: large_dtm_filled.tif

# Normalized Height above Ground:

execute

pdal pipeline .\hag_dem.json --verbose 4
