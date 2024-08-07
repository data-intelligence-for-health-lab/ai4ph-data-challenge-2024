# ai4ph-data-challenge-2024
This is the main site for the 2024 AI4PH Summer Institute Data Challenge.

## Project Background
Material and social deprivation are critical issues affecting urban populations worldwide. These forms of deprivation refer to inadequate access to essential resources, such as income, housing, healthcare, education, and social services, leading to significant disparities in quality of life. Traditional methods of assessing deprivation rely heavily on socio-economic surveys and administrative data, which can be resource-intensive and may not provide a real-time or comprehensive view of urban environments.

Recent advances in computer vision and deep learning offer new opportunities to analyze urban environments using street-level imagery. Street-level images provide a rich visual context that can capture subtle indicators of deprivation, such as the condition of buildings, presence of litter, and availability of community services. By leveraging these visual cues, it is possible to develop automated systems that can assess material and social deprivation more efficiently and accurately.

## Data Challenge Goals
This Data Challenge aims to study the association between urban environments and material and social deprivation status. The urban environment can be understood by street-level images. We have provided the street view images from five Canadian cities and public health related data - Material and Social Deprivation indices. You and your team should apply deep learning algorithms you learned to extract street features (i.e., greenness, sky proportion, pedestrian count, etc.) and raise appropriate research questions to provide insights into Canadian urban public health.

Possible objectives include but not limited to: 
- Develop a deep learning model that analyzes street-level images of urban environments to assess material and social deprivation status. This model will leverage computer vision techniques to identify indicators of deprivation and predict the deprivation indices.
- Employ a deep learning model to detect objects from images and correlate them with deprivation using statistical modelling.
- Analyze feature importance.

For example, you could come up with the hypothesis that areas with higher levels of greenness, better-maintained roads and sidewalks have lower material and social deprivation. You could then design your experiments accordingly to generate results to test this hypothesis. Again, this is just one example.

## Data Set
Each group is provided with a Google account that has been pre-loaded with data from one city. Each group is assigned to a city as follows:
- Group 1: Calgary
- Group 2: Vancouver
- Group 3: Winnipeg
- Group 4: Toronto
- Group 5: Montreal

### Google Street View (GSV) Images

We randomly selected 1000 postal codes for each city, and each postal code contained 12 images. You do not need to use all images but analyze them based on the specific research questions you raise. Using fewer images will reduce computational time, which will be helpful when you are experimenting with different ideas initially.

|  |  |  |
| --- | --- | --- |
| ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/c3c5bdbc-78ff-4006-9db0-7bc4f25c6663) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/1edc8048-51d5-4879-8e76-2142b50f53b9) |![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/d41f8e2a-83fe-424a-9cd1-42d130252eef) |
| T0A0A6_0_0.jpg | T0A0A6_0_60.jpg | T0A0A6_0_120.jpg |
| ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/87c3425e-f2d0-4419-bf2f-8cf9e06f2a14) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/234b0891-06bf-4aea-a50f-62e828e724f3) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/662f54f4-7d95-44ef-9e06-381b51492fa8) |
| T0A0A6_0_180.jpg | T0A0A6_0_240.jpg | T0A0A6_0_300.jpg |
| ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/57e23f7d-2b08-47bf-a786-2cdcfd045cc3) |![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/4a0c71e1-e8fd-4225-9e09-df33a51a2841) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/5a79dda3-2273-4118-92e1-8e486b7a8ce3) |
| T0A0A6_60_0.jpg | T0A0A6_60_60.jpg | T0A0A6_60_120.jpg |
| ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/40a79c75-704f-40b4-8069-d0cbb77a9173) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/b90783cb-a346-4f04-b9ad-b379a7e38d58) | ![image](https://github.com/data-intelligence-for-health-lab/ai4ph-data-challenge-2024/assets/134657579/91efb5c4-b476-4fe0-ba1d-16537345662a) |
| T0A0A6_60_180.jpg | T0A0A6_60_240.jpg | T0A0A6_60_300.jpg |

The GSV images were scraped for the following published paper: https://www.nature.com/articles/s41598-022-22630-1. Images are at the postal-code level and are grouped by city. For each postal code, 12 images are provided. Six of them were taken at a 0-degree angle from the horizontal line and the other six were at 60 degrees. At the same horizontal angle, the camera was rotated 60 degrees each time to take a picture, ending up with six angels: 0°, 60°, 120°, 180°, 240°, 300°. For example (see below), ‘T0A0A6_0_120.jpg’ shows a picture taken at a 0-degree horizontal angle, and 120° rotated and the postal code is T0A0A6.

Image features, including persons, bicycles, vehicles, sky, greenness, etc., can be extracted using deep learning algorithms for image classification (e.g., PSPNet - https://github.com/segcv/PSPNet) or object detection (e.g., Yolo - https://github.com/ultralytics/ultralytics).

### Metadata Table

We also provided a metadata table that links the postal codes of each city to their deprivation indices (material and social deprivation status). This table contains 5 columns: postal code (POSTALCODE_15), city name (COMM_NAME_15), dissemination area (DA), material deprivation (SCOREMAT), and social deprivation (SCORESOC). 
		
Please note that for SCOREMAT and SCORESOC lower scores (e.g., below zero) indicate a better status (less deprivation), while scores higher than zero indicate a worse status (more deprivation).

## Example Code
Example code is provided in this repo which collectively includes the steps below. Please use the example code as a starting point and modify it appropriately to suit your objectives. You are welcome to try new methods that are outside of the example code but please be mindful of the limited time you have to work on this Data Challenge.
 
## Computational Environment and Time
It would be easiest if you work on the Data Challenge within Google Colab. You can either use the Google account provided to your team or your personal Google account if you wish, but please try to access the data set as shown in the example code rather than copying and moving them out of the provided account (see below regarding data privacy).

The free version of Google Colab will be sufficient to run your code within reasonable time (30-45 min for most relatively heavy jobs being run on all 1000 postal codes). If you want to quickly pilot something, you may want to use a subset of the data. You may want to run heavy jobs overnight to be efficient with your time. 

## Tools and Techniques
- Programming Languages: Python
- Deep Learning Frameworks: TensorFlow, Keras, PyTorch
- Image Processing Libraries: OpenCV, scikit-image, Yolo - https://github.com/ultralytics/ultralytics, PSPNet - https://github.com/segcv/PSPNet
- Data Analysis Libraries: pandas, NumPy, SciPy
- Visualization Tools: Matplotlib, Seaborn, Plotly

## Data Privacy
The provided data set can only be used for this Data Challenge. **If you make any copies of the data set and store them outside of the provided Google account, please destroy them once the Summer Institute ends!** It would be ideal to simply access the data in the provided Google account as shown in the example code (from within the provided Google account or your personal Google account) rather than copying them to your local machine or personal Google account. 
  
## Deliverable
All groups are required to give a presentation that adheres to the following:
  - Clearly state your group's research questions, hypotheses, and/or objectives.
  - Describe the methods your group undertook.
  - Present the results and draw conclusions.
  - Discuss limitations and other approaches that could have been pursued.
  - Describe each team member's contributions
  - Share any other learnings!
  - 15 minutes for the presentation + 5 minutes of Q&A per group.

