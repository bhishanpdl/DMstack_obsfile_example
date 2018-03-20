# Using Cluster module to estimate the mass of the cluster

The steps are following:
```
1) python clusters_import_simcat.py # filenames are hard coded
2) clusters_zphot.py sim.yaml sim.hdf5
3) clusters_mass.py sim.yaml sim.hdf5
```

The file `sim.yaml` looks like this:  
```
{
    "cluster": "SIM_cluster",
    "ra": 0.1,
    "dec": 0.1,
    "redshift": 0.3,
    "filter": ["u", "g", "r", "i", "i2", "z"],
    "butler": "/home/bhishan/Research/a2_dmstack/dmstack_example/example/output",
    "keys": {'src':["id", "coord*", "ext_shapeHSM_HsmSourceMoments_x", "ext_shapeHSM_HsmSourceMoments_y", "ext_shapeHSM_HsmShapeRegauss_e1", "ext_shapeHSM_HsmShapeRegauss_e2"]},
    "sim": {"flag" : True, "zfile":"sim.txt"},
    "mass":{ "zconfig" : "zphot_ref",
             "mprior":'lin'}
}
```