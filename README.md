sofia-ml, modified
==================

This is a slightly modified version of [sofia-ml](http://code.google.com/p/sofia-ml/) by D. Sculley. It differs from the original only in one additional parameter used with RBF cluster mapping:

`--cluster_mapping_threshold <t>`

After mapping, the values below the threshold will be set to zero (try `t` = 0.01 or 0.001). The resulting file will be smaller and sparsyifying in this way may also help supervised learning (smaller error in classification or regression).

Make sure that `t` is small enough in relation to `--cluster_mapping_param`, because if all the features are smaller than the threshold, you'll just get a bunch of zeros.

The modified files are:

	sofia-ml/cluster-src/sf-cluster-centers.cc
	sofia-ml/cluster-src/sf-cluster-centers.h
	sofia-ml/src/sofia-kmeans.cc

See [http://fastml.com/the-secret-of-the-big-guys/](http://fastml.com/the-secret-of-the-big-guys/) for more.