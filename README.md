# DataScientist assessmnet for Norfolk Southern
1 Center point dectection for PASCAL-VOC images with a single object \\
  1.1 Constraints and Requirements \\ 
    • Use Jupyter notebook for all the stages from the beginning to the end. Provide a write-up for your solution.\\
      – Hint: one of the essential skills for a successful data scientist is to be able to present the results decently
        and fluently to the business partners with no technical background. A nice write-up will be a key in
        evaluating the candidate.
    • Provide details on the version of the tools and packages used.
    • Only use Tensorflow and/or Keras. PyTorch or other frameworks are not allowed.
    • Do not publically post solution to Github, Stackoverflow, etc.
    • Do not use any code from Github or other internet sources.
  1.2 Explanation of Data
    • Located under ./data
    • ./data/Annotations:
      – Set of XML files that contain metadata for each image - which include: bounding box info, class info,
        etc.
    • ./data/ImageSets/Main:
      – Only use files of "aeroplane", "car", "cat", and "dog".
      – Use only the files ending with "train" and "val"
      – Each file (which is for each class), contains:
          * Image name
          * +1: image contains the class
          * -1: image does not contain the class
    • JPEGImages:
      – Main set of images to be used
  1.3 Tasks
    • Construct train and validation sets
      – Hint: you can simply use _train and _val flags in data/ImageSets/Main, which may need some
        parsing.
    • From the train and validation sets, find images with classes: aeroplane, car, cat, dog.
    • Eliminate all other class information for these images (e.g. for the image with dog and bicycle, remove bicycle
      information).
    • Reduce image set to only those images with a single object (of the four classes of interest) i.e. if an image
      has two or more dogs, remove that image (you will only keep the images that contain 1 cat, or 1 dog, or 1
      aeroplane, or 1 car)
    • From the bounding box information, compute center point of the object for each image.
    • Create a Deep Learning model whose input is an image with a single object of the given classes and output is
      the centerpoint class of that object - not a bounding box.
      – Note: Post-processing is not allowed i.e. the last layer of the network should not output bounding box
        coordinates. The last layer of network should only output centerpoint.
      – Note: the last layer of the network cannot be a fully-connected layer.
    • Evaluate your model:
      – Create a confusion matrix of predicted vs ground truth classes
      – Report the RMSE of predicted vs ground truth center.
    • Give explanation of model and why you chose the design (including choice of loss function, optimizer, etc).
    • Provide details of what you would have done to improve your results if you were given infinite time/resources.
