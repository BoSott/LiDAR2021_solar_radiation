# OPALS, calculate normals
## base layer with trees
opalsImport -inf .\large_baselayerWithTrees.xyz -iformat .\import_def.xml -tileSize 60
opalsNormals -inf .\large_baselayerWithTrees.odm -neigh 16 -searchMode d3 -searchRad 1
opalsExport -inf .\large_baselayerWithTrees.odm -outf large_baselayerWithTrees_normals.xyz -oformat export_def.xml

## base layer no trees
opalsImport -inf .\large_baselayer.xyz -iformat .\import_def.xml -tileSize 60
opalsNormals -inf .\large_baselayer.odm -neigh 16 -searchMode 3d -searchRad 1
opalsExport -inf .\large_baselayer.odm -outf large_baselayer_normals.xyz -oformat export_def.xml

# VOSTOK
execute

.\vostok.exe sol_file.sol

the vostok exe, the sol_file and the input datasets have to be in the same folder
