#  Age-Sex Detector

Deep Learning (Convolutional Neural Network) model to predict the age and sex from face images (UTKFace dataset), achieving 0.92 test sex accuracy and 8.68 test age RMSE

- [Data](#data)
  - [Data Explanation](#data-explanation)
- [Model Full](#model-full)
- [Model Cropped](#model-cropped)
  - [Dash images](#dash-images)
- [Steps to run web app](#steps-to-run-web-app)
  

## Data

[UTKFace dataset](https://susanqq.github.io/UTKFace/)

[UTKFace dataset Kaggle](https://www.kaggle.com/jangedoo/utkface-new)

This dataset contains over 20,000 face images with annotations of
age, sex, and ethnicity. The images cover large variation in pose, facial expression, 
illumination, occlusion, resolution, etc.

### Data Explanation

If a photo is called __34_0_0_201701171712010149082.jpg.chip.jpg__, it means that the age of the individual is 34 and his sex is male. 
That is, the photo names follow the following scheme __age_sex_race_relevant_data.jpg.chip.jpg__.

Sex being 0 for male and 1 for female.


## Model Full

We have used Convolutional Neural Networks (CNN) to predict the age and sex of the **full** input image.

We have obtained the following metrics:
- Validation:
  - Sex accuracy: 0.869
  - Age MSE: 135.65
  - Age MAE: 8.54
- Test:
  - Sex accuracy: 0.878
  - Age MSE: 140.35
  - Age MAE: 8.68


## Model Cropped

We have used Convolutional Neural Networks (CNN) to predict the age and sex of the **cropped** input image.

We have obtained the following metrics:
- Validation:
  - Sex accuracy: 0.905
  - Age MSE: 78.956
- Test:
  - Sex accuracy: 0.915
  - Age MSE: 75.28

### Dash images

Prediction tool (the age has an error margin):
![prediction](cropped/example_imgs/prediction.png)

Saliency maps:
![saliency_maps](cropped/example_imgs/saliency_maps.png)

Model metrics (best model selected):
![metrics](cropped/example_imgs/metrics.png)

## Steps to run web app

From the main project folder (AgeSexDetector/) run the following command:

```shell
pip install -r requirements.txt
```

Then, from one of the main folders (AgeSexDetector/full/ or AgeSexDetector/cropped/) run the following command:

```shell
python -m dashboard.dashboard
```




