sofia-ml, modified
==================

This is a modified version of [sofia-ml](http://code.google.com/p/sofia-ml/) by D. Sculley. It differs from the original only in two additional parameters for sofia-kmeans RBF cluster mapping:

`--cluster_mapping_threshold <float t>`

After mapping, the values below the threshold will be set to zero (try `t` = 0.01 or 0.001). The resulting file might be smaller and sparsyifying in this way may also help supervised learning (smaller error in classification or regression).

Make sure that `t` is small enough in relation to `--cluster_mapping_param`, because if all the features are smaller than the threshold, you'll just get a bunch of zeros.

`--cluster_mapping_sparsity <int s>`

Only use _s_ nearest cluster centers for mapping. It is a stronger alternative to setting a threshold. The results with sparse mapping might be slightly worse, but the file certainly will be way smaller. Recommended for large data sets.


The modified files are:

	sofia-ml/cluster-src/sf-cluster-centers.cc
	sofia-ml/cluster-src/sf-cluster-centers.h
	sofia-ml/src/sofia-kmeans.cc

See [http://fastml.com/the-secret-of-the-big-guys/](http://fastml.com/the-secret-of-the-big-guys/) for more.

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/zygmuntz/sofia-ml-mod/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

