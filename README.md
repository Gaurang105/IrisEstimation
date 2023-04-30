
# Eye Tracking with ResNet50 and TensorFlow

This repository contains a Python script for training an eye-tracking model using the ResNet50 architecture in TensorFlow. The script reads image and label data from a given directory, preprocesses the images, and then trains a model to predict the location of eyes in the images. The trained model can then be used to predict eye locations in real-time video streams.




## Requirements

The script requires the following Python packages:

- TensorFlow
- OpenCV
- Matplotlib
You can install these requirements using pip:

```python
pip install tensorflow opencv-python matplotlib
```


## Training Data

The training data should consist of images and corresponding label files in JSON format. The images and labels should be organized into train, test, and validation subdirectories, each containing images and labels subdirectories. The labels should be JSON files containing a 'keypoints' array with the coordinates of the eyes in the image.

For example, your directory structure should look something like this:

```bash
aug_data
├── train
│   ├── images
│   └── labels
├── test
│   ├── images
│   └── labels
└── val
    ├── images
    └── labels
```

## Usage

To train the model, simply run the IrisEstimation .ipynb notebook. It will load the data, train the model, and save the trained model as 'eyetrackerresnet.h5'.

To use the trained model for real-time eye tracking, the script captures frames from your computer's default camera, preprocesses them, and uses the model to predict the location of the eyes in each frame. It then displays the frames with the predicted eye locations marked.


## Results

The script plots and shows the loss and validation loss of the model over the training epochs, allowing you to see how the model's performance improved over time. After training, it also displays some sample predictions on the test data.

Finally, it shows the real-time eye tracking results on frames captured from the camera.


## Note

This is a simple script for demonstration purposes and may need to be adjusted for your specific needs. The quality of the predictions will depend on the quality and variety of the training data, batch size and epochs. In this I've used 8 batch size, 50% of my dataset, 20 epoch and ResNet50 so it's not accurate completely.

Ideally: 
- 16 Batch size
- 100 Epoch
- ResNet152V2
- More 7000 image dataset
