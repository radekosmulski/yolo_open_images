**If weights do not download for you, chances are the repository is over the git lfs quota. Please pull from the [bitbucket repository](https://bitbucket.org/dreamwalkerrr/yolo_open_images/src/master/) which does not have this limitation.**

This repository contains yolov3 weights along with config files. The model achieves an mAP of 42.407 on the private LB for the [Kaggle Open Images challenge](https://www.kaggle.com/c/google-ai-open-images-object-detection-track/leaderboard).

In order to use these weights you will need to have [darknet](https://github.com/pjreddie/darknet) installed. You can read more about it on the [project website](https://pjreddie.com/darknet/yolo/).

There are multiple ways to use darknet for detection. One way would be to create a txt file with paths to images you would like to run detection on and pointing to that file from the included yolo.data file.

The command to run detection (assuming darknet is installed in the root of this repo) is:
`./darknet/darknet detector valid yolo.data yolov3-spp.cfg yolov3-spp.backup`

I am sharing these weights on the assumption that they might be useful to someone. I am unable to provide any support should you encounter any issues. Yolo is not very easy to troubleshoot and if you get a segfault it is up to you to figure out what went wrong.

Having said that, the config files here worked for me and are a useful starting point. Note that class names are prefixed by '/m/'. This prefix has been removed from yolo.names. Having this prefix there interferes with creating output files.

Here is the citation for the paper that introduces yolov3:
> @article{yolov3,
>   title={YOLOv3: An Incremental Improvement},
>   author={Redmon, Joseph and Farhadi, Ali},
>   journal = {arXiv},
>   year={2018}
> }

I provide a brief overview of how I trained the model [here](https://www.kaggle.com/c/google-ai-open-images-object-detection-track/discussion/64734).
