Object_Discovery
================

Object Discovery Algorithm on Egocentric Images.

Usage:

	For a single object discovery execution: 
		- Modify the parameters in loadParameters.m
		- Run main.m
	
	For a battery of tests: 
		- Comment the first line in main.m
		- Change the parameters in tests_battery.m and run it.
	
	If you want to use the Multiscale Combinatorial Grouping (MCG) Objectness [4]:
		- Download from the authors page: http://www.eecs.berkeley.edu/Research/Projects/CS/vision/grouping/mcg/
		- Configure installation path in loadParameters.m
	
	If you want to use the CNN features [7] extraction:
		- Install Caffe: http://caffe.berkeleyvision.org/
		- Configure installation path in loadParameters.m
		- Download the "bvlc_reference_caffenet.caffemodel" network model.
		- Copy network model into Object_Discovery/Caffe Src/bvlc_reference_caffenet
   

Explanation and additional features:

	This function is inspired by the pipeline proposed by 
       	K. Grauman in [1] with the following modifications:
       		- Added Ferrari's Objectness [2], BING Objectness [3],
               		Multiscale Combinatorial Grouping (MCG) [4] and
               		Selective Search [6].
           	- Added iterative Scene-Object discovery by turns.
           	- Added Scene Awareness to the set of features.
           	- Added Scene Score to the set of easiness scores.
           	- Added Dimensionality Reduction based on LSH.
           	- Added Locality Sensitive Hashing, K-Means, LSK+K-Means and 
               		Ward instead of Complete-Link clustering for the grouping 
               		of the easiest instances.
           	- Added clustering by levels (using a different set of 
               		features at each of them.
           	- Adaptable for huge datasets (e.g. SenseCam or Narrative 
               		lifelogging data).
           	- Added CNN features [5,7] extraction for object candidates 
               		and scenes.
           	- Added PCA dimensionality reduction on easy objects.
           	- Added initial ObjVsNoObj RBF-SVM classifier for discarding
			the majority of No Objects.

References:

       [1] Lee, Yong Jae, and Kristen Grauman. "Learning the easy things 
           first: Self-paced visual category discovery." Computer Vision 
           and Pattern Recognition (CVPR), 2011 IEEE Conference on. IEEE, 
           2011.
       [2] Alexe, Bogdan, Thomas Deselaers, and Vittorio Ferrari. "What 
           is an object?." Computer Vision and Pattern Recognition (CVPR), 
           2010 IEEE Conference on. IEEE, 2010.
       [3] Cheng, Ming-Ming, et al. "BING: Binarized normed gradients for 
           objectness estimation at 300fps." IEEE CVPR. 2014.
       [4] Arbeláez, Pablo, et al. "Multiscale Combinatorial Grouping." 
           CVPR, 2014.
       [5] Krizhevsky, Alex, Ilya Sutskever, and Geoffrey E. Hinton. 
           "Imagenet classification with deep convolutional neural 
           networks." Advances in neural information processing systems. 
           2012.
       [6] Uijlings, Jasper RR, et al. "Selective search for object 
           recognition." International journal of computer vision 104.2 
           (2013): 154-171.
       [7] Jia, Yangqing, et al. "Caffe: Convolutional architecture for 
           fast feature embedding." Proceedings of the ACM International 
           Conference on Multimedia. ACM, 2014.
