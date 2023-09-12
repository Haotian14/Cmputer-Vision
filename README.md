# Cmputer-Vision
## Dataset
The dataset to be used in the group project is the Penguins versus Turtles dataset available
from Kaggle (see reference at the end of this document). It consists of a training set of 500
images and a validation set of 72 images. Each image contains either a penguin or a turtle, in
an arbitrary location, as indicated in the corresponding annotation files.
## Detection
The first task is to detect and localize the animal in each image. Specifically, the task is to
develop a method that can take any image from the dataset as input and produce a bounding
box as output (x_min, y_min, width, height, all in pixels).
It is up to you whether you solve this as a stand-alone task, or whether you first solve the
classification task (described next) and then use the predicted class label to inform the
detection (as this allows to employ a more dedicated detector for each class), or even whether
you somehow solve the two tasks jointly.
## Classification
The second task is to classify the animal in each image. Specifically, this task is to develop a
method that can take any image from the dataset as input and produce a class label as output
(1 = penguin, 2 = turtle).
It is up to you whether you solve this as a stand-alone task, or whether you first solve the
detection task (described above) and then use the predicted bounding box to inform the
classification (as this allows to focus on the animal and ignore the larger background), or even
whether you somehow solve the two tasks jointly.
## Methods
Many traditional and/or machine/deep learning-based computer vision methods could be
used for these tasks. You are challenged to use concepts taught in the course and other
methods from literature to develop your own method and evaluate its performance.
The codes of some popular detection and classification methods are publicly available. You
can study them for inspiration, but you should not use them directly (we will check whether
you used existing code or not, see the notes above and below).
Although we do not expect you to develop everything from scratch, we do expect to see some
new combination of methods, or some tweaks of existing methods, or the use of more state-
of-the-art methods that have not been tried before for the given problem.
As there are virtually infinitely many possibilities here, it is impossible to give detailed criteria,
but as a general guideline, the more you develop yourself rather than copy straight from
elsewhere, the better. In any case, always do cite your sources.
## Training
If your methods require training (that is, if you use supervised rather than unsupervised
detection and classification approaches), you can use the training set (500 images) for this
purpose. Even if your methods do not require training, they may have hyperparameters that
you need to fine-tune to get optimal performance. In that case, too, you must use the training
set, not the validation set, because using (partly) the same data for both training/fine-tuning
and testing leads to biased results that are not representative of actual performance.
## Testing
For the testing of your method, you must use the validation set (72 images). To assess the
overall performance of the method, calculate and report the following metrics.
Detection performance: For each validation image, calculate the distance between the centre
location of the predicted bounding box and the centre location of the corresponding true
bounding box (available from the annotation file), and report the mean and standard deviation
of the distances over all validation images. Also calculate the intersection over union (IoU) of
the predicted bounding box and its corresponding true bounding box for each validation image
and report the mean and standard deviation.
Classification performance: For each validation image, use the true class label (available from
the annotation file) to determine whether the predicted class label is correct or not, and report
the confusion matrix of the classification results. From this, calculate and report the accuracy,
precision, recall, and the F1-score of your method.
Show these quantitative scores in your demo and written report (see deliverables below) and
also show representative examples of successful detections and classifications as well as
examples where your method failed (no method generally yields 100% perfect results). Give
some explanation why you believe your method failed in these cases.
## Visualisation
In addition to quantitative testing (described above) your method must also show the
detection and classification result. That is, for each image, it should not only detect and classify
the animal, but also draw its corresponding bounding box and class label onto the image.
