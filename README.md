# ai4ph-data-challenge-2024
This is the main site for the 2024 AI4PH Summer Institute Data Challenge.

## Project background
Material and social deprivation are critical issues affecting urban populations worldwide. These forms of deprivation refer to inadequate access to essential resources, such as income, housing, healthcare, education, and social services, leading to significant disparities in quality of life. Traditional methods of assessing deprivation rely heavily on socio-economic surveys and administrative data, which can be resource-intensive and may not provide a real-time or comprehensive view of urban environments.

Recent advances in computer vision and deep learning offer new opportunities to analyze urban environments using street-level imagery. Street-level images provide a rich visual context that can capture subtle indicators of deprivation, such as the condition of buildings, presence of litter, and availability of community services. By leveraging these visual cues, it is possible to develop automated systems that can assess material and social deprivation more efficiently and accurately.

## Project objective
This Data Challenge project aims to study the association between urban environments and material and social deprivation status. The urban environment can be understood by street-level images. We have provided the street view images from five Canadian cities and public health related data - Material and Social Deprivation indices. You and your team should apply deep learning algorithms you learned to extract street features (i.e., greenness, sky proportion, pedestrian count, etc.) and raise appropriate research questions to provide insights into Canadian urban public health.

For example: 
- Develop a deep learning model that analyzes street-level images of urban environments to assess material and social deprivation status. This model will leverage computer vision techniques to identify indicators of deprivation and predict the deprivation indices.
- Develop a deep learning model to detect objects from images and correlate them with deprivation using statistical modelling.
- Feature importance analysis

Each group will be assigned:
- a Google account with Colab Pro; create 5 Google accounts/collab, ai4ph data challenge team 1-5, upload data.
- The data for one of the five cities.

## Datasets

The study area included data from five large cities across Canada: Vancouver, Calgary, Winnipeg, Toronto, and Montreal. We randomly selected 1000 postal codes for each city, and each postal code contained 12 images. You and your group will be assigned one city to analyze. You do not need to use all images but analyze them based on the specific research questions you raise. 

We provided a data table that linked the postal codes of each city to their deprivation indices (material and social deprivation status):
- The dataset contains 5 elements, such as postal code (POSTALCODE_15), city name (COMM_NAME_15), dissemination area (DA), material deprivation (SCOREMAT), and social deprivation (SCORESOC), which are linked from 3 individual tables. 
		
Notes: for SCOREMAT and SCORESOC, lower scores (e.g., below zero) indicate a better status (less deprivation), while scores higher than zero indicate a worse status (more deprivation).

- The image dataset

![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/c3c5bdbc-78ff-4006-9db0-7bc4f25c6663)   ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/1edc8048-51d5-4879-8e76-2142b50f53b9)   ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/d41f8e2a-83fe-424a-9cd1-42d130252eef) 

T0A0A6_0_0.jpg T0A0A6_0_60.jpg T0A0A6_0_120.jpg
     |

| --- | --- | --- |
| git status | List all new or modified files | List all new or modified files |
| git diff | Show file differences that haven't been staged | List all new or modified files |


The datasets are Google Street View (GSV) images of major cities in Canada, which are scrapped for the following published paper https://www.nature.com/articles/s41598-022-22630-1. Images are postal-code level and are grouped by cities. For each postal code, 12 images are included. Six of them were taken at a 0-degree angle from the horizontal line and the other six were at 60 degrees. At the same horizontal angle, the camera was rotated 60 degrees each time to take a picture, ending up with six angels: 0°, 60°, 120°, 180°, 240°, 300°. For example (see below), ‘T0A0A6_0_120.jpg’ shows a picture taken at a 0-degree horizontal angle, and 120° rotated and the postal code is T0A0A6.

Image features, including persons, bicycles, vehicles, sky, greenness, etc., can be extracted through deep learning algorithms, like Image Classification (PSPNet - https://github.com/segcv/PSPNet) and Object Detection (Yolo - https://github.com/ultralytics/ultralytics) .

## Project outline
### For example, you could come up with the hypothesis that areas with higher levels of greenness, better-maintained roads and sidewalks have lower material and social deprivation.

- Data collection
  - Choose the data from one of the five cities.
- Data preprocessing
  - Feature extraction: Use computer vision techniques (e.g., CNNs, object detection, image segmentation) to extract features from the images.
- Model development
  - Develop machine learning models (e.g., random forests, gradient boosting, neural networks) to predict deprivation indices based on extracted features.
- Training and validation
  - Using the annotated dataset, optimizing for performance metrics such as accuracy, precision, recall, and F1-score.
- Feature analysis and correlation
  - Conduct feature importance analysis to identify the most significant predictors of deprivation.
- Evaluation and impact
  - Test the models on unseen data to evaluate their robustness and generalizability.
  - Provide visualizations or insights about urban public health based on the model results.

## Tools and techniques
- Programming Languages: Python
- Deep Learning Frameworks: TensorFlow, Keras, PyTorch
- Image Processing Libraries: OpenCV, scikit-image, Yolo - https://github.com/ultralytics/ultralytics, PSPNet - https://github.com/segcv/PSPNet
- Data Analysis Libraries: pandas, NumPy, SciPy
- Visualization Tools: Matplotlib, Seaborn, Plotly

## Challenges and considerations
- Data Privacy: Ensure the collection and use of street-level images comply with privacy regulations and ethical standards. Destroy the data after the completion of the summer institute. 
  
## Expected outcomes
- Deprivation prediction method: A robust deep learning model capable of predicting material or social deprivation from street-level images.
- Presentation (key components)
  - Research question: List and explain the hypotheses regarding indicators of deprivation from street features
  - Insightful analysis: The understanding of the visual indicators of deprivation and their correlations to deprivation or urban public health.
  - Timing requirements: 15 mins (Presentation) + 5 mins (Q&A), 2 hours in total, 5 groups

