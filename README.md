# pyflann3

### Introduction
pythhon 3 version of [pyflann](https://github.com/primetang/pyflann).

### Install

	git clone https://github.com/AlbertZhangHIT/pyflann3
	cd pyflann
	python setup.py install

### Usage
Example:


	from pyflann import *
	import numpy as np
	
	dataset = np.array(
	    [[1., 1, 1, 2, 3],
	     [10, 10, 10, 3, 2],
	     [100, 100, 2, 30, 1]
	     ])
	testset = np.array(
	    [[1., 1, 1, 1, 1],
	     [90, 90, 10, 10, 1]
	     ])
	flann = FLANN()
	result, dists = flann.nn(
	    dataset, testset, 2, algorithm="kmeans", branching=32, iterations=7, checks=16)
	print(result)
	print(dists)
	
	dataset = np.random.rand(10000, 128)
	testset = np.random.rand(1000, 128)
	flann = FLANN()
	result, dists = flann.nn(
	    dataset, testset, 5, algorithm="kmeans", branching=32, iterations=7, checks=16)
	print(result)
	print(dists)