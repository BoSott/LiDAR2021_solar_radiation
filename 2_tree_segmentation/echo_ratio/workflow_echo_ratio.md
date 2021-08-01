opalsImport -inf large_ds.las
opalsNormals -inf large_ds.odm -neighb 10 -searchR 10.0
opalsEchoRatio -inFile large_ds.odm -ratioMode slopeA -searchRadius 3.0
opalsExport -inf large_ds.odm -outf large_ds_ER_test.xyz -oFormat format_ER.xml

# additionally possible:
CloudCompare -> height extraction and SOR with 80NN and 1std
