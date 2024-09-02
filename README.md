# Cloudscape-Insights

Project which classifies satillite images of clouds into 4 classes [fish,flower,gravel,sugar]

Data is taken from the kaggle competition of "Understanding Clouds using Satellite Images" and solution is submitted to kaggle You can check it out on my profile and also see my other learnings on kaggle: https://www.kaggle.com/teluguyogesh

Description:

Climate change has been at the top of our minds and on the forefront of important political decision-making for many years. We hope you can use this competition’s dataset to help demystify an important climatic variable. Scientists, like those at Max Planck Institute for Meteorology, are leading the charge with new research on the world’s ever-changing atmosphere and they need your help to better understand the clouds.

Shallow clouds play a huge role in determining the Earth's climate. They’re also difficult to understand and to represent in climate models. By classifying different types of cloud organization, researchers at Max Planck hope to improve our physical understanding of these clouds, which in turn will help us build better climate models.

There are many ways in which clouds can organize, but the boundaries between different forms of organization are murky. This makes it challenging to build traditional rule-based algorithms to separate cloud features. The human eye, however, is really good at detecting features—such as clouds that resemble flowers.

In this challenge, you will build a model to classify cloud organization patterns from satellite images. If successful, you’ll help scientists to better understand how clouds will shape our future climate. This research will guide the development of next-generation models which could reduce uncertainties in climate projections.

Help us remove the haze from climate models and bring clarity to cloud identification.

For more information on the scientific background and how the labels were created see the following paper.

Evaluation
This competition is evaluated on the mean Dice coefficient. The Dice coefficient can be used to compare the pixel-wise agreement between a predicted segmentation and its corresponding ground truth. The formula is given by:

2∗|X∩Y||X|+|Y|
where X is the predicted set of pixels and Y is the ground truth. The Dice coefficient is defined to be 1 when both X and Y are empty. The leaderboard score is the mean of the Dice coefficients for each <Image, Label> pair in the test set.

EncodedPixels
In order to reduce the submission file size, our metric uses run-length encoding on the pixel values. Instead of submitting an exhaustive list of indices for your segmentation, you will submit pairs of values that contain a start position and a run length. E.g. '1 3' implies starting at pixel 1 and running a total of 3 pixels (1,2,3).

The competition format requires a space delimited list of pairs. For example, '1 3 10 5' implies pixels 1,2,3,10,11,12,13,14 are to be included in the mask. The metric checks that the pairs are sorted, positive, and the decoded pixel values are not duplicated. The pixels are numbered from top to bottom, then left to right: 1 is pixel (1,1), 2 is pixel (2,1), etc.

IMPORTANT
The predicted encodings should be against images that are scaled by 0.25 per side. In other words, while the images in Train and Test are 1400 x 2100 pixels, the predictions should be scaled down to a 350 x 525 pixel image. The reduction is required to achieve reasonable submission evaluation times.

Submission File Format
Your submission file should be in csv format, with a header and columns names : Image_Label, EncodedPixels. Each row in your submission represents a single predicted cloud type segmentation for the given Image, and predicted Label, and you should have the same number of rows as num_images * num_labels. The segment for cloud type in an image will be encoded into a single row, even if there are several non-contiguous cloud type locations in an image. If there is no area of a certain cloud type for an image, the corresponding EncodedPixels prediction should be left blank.

# some EDA

![image](https://github.com/user-attachments/assets/73a6a569-9dee-447c-a8ba-fa7e44fb226d)

![image](https://github.com/user-attachments/assets/6488aab5-5fc7-4fa6-ac51-06a6f7b55238)

![image](https://github.com/user-attachments/assets/79148b41-ec2a-474c-9186-8d90cac0021c)

![image](https://github.com/user-attachments/assets/a3ca60f2-8847-45ea-b7fb-25c63cea6610)

![image](https://github.com/user-attachments/assets/92cf9ed0-e43f-4bbb-b01d-134f2da4cd67)

![image](https://github.com/user-attachments/assets/7b7d7de0-fcb1-4a71-8841-8be1b315cbd0)

![image](https://github.com/user-attachments/assets/fa33b285-777a-4bb3-8fe3-4007ad009355)

Future scope : this model can be saved as the .h5 file and can be deployed on servers to integrate it in the applications required like a webapp etc
