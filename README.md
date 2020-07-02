## Abstract
We attempted to address the problem of classifying planned/unplanned localities. Localities categorization could assist municipality in proper allocation of resources. However,  a variety of factors have to be incorporated for any such classification, which makes this a complex task. To tackle all such intricacies, we propose a deep learning approach for classifying different areas using satellite imagery. We propose a multi-task learning framework that learns variety of features from the satellite images and finds the one most effective for classifying planned or unplanned developments. For training and evaluation of our proposed method we have compiled a dataset containing labelled satellite images  of three geographically diverse cities of Pakistan. Our experimental results validate the proposed technique

## Overview
This blog post is going to be pretty long! Here’s an overview of the different sections. If you want to skip ahead, just click the section title to go there.

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Building Segmentation](#building-segmentation)
- [Multi Task Learning](#multi-task-learning)
- [Evaluation](#evaluation)
- [Conclusion](#conclusion)

## Introduction
Majority  of  the  urban  applications:    development  ofcities, urban planning, provisioning municipal services, andcadastral inspection require detailed information and obser-vation of an area.  Generally, such information is collected by utilizing on ground authorities and volunteers. However, collecting all this information via on-ground forces is not feasible. Consequently, satellite imagery is being used for the purpose of ground information collection. Over the last decade deep neural networks have shown exceptional capability to learn complex patterns in digital data.  These techniques can be applied for detecting different patterns and structures in satellite imagery and classify satellite images as planned or unplanned localities.

### The Problem
We attempted to address the problem of classifying planned/unplanned localities. Localities categorization could assist municipality in proper allocation of resources.However,  a variety of factors have to be incorporated for any such classification, which makes this a complex task.

### The Solution
We propose a deep learning approach for classifying different areas using Remote sensing data. We propose a multi-task learning framework that learns variety of features from the satellite images and finds the one most effective for classifying planned or unplanned developments. Using these features we calculate planned locality index for each image by applying analytical hirearchical processing technique.

### Software and Hardware
We have mainly used Python, NumPy and Keras to implement our solution. All our experiments have been performed using Google's colaboratory service. To replicate these experiments successfully GPU based runtime of colaboratory is required.
  
## Dataset
For this research project we have used two different datasets. The first one is called Village Finder **Village Finder paper ka reference**. We used this dataset to train a model for building segmentation. To train our multi task learning model we had compiled a separate data set containing satellite images of different cities of pakistan.

### Village Finder
Village Finder Dataset contains 3566 images where each image is of 256 x 256 pixels. Corresponding to each image we have masked images that act as labels for building segments in that image. We used this dataset to train a model for building segmentation. This model is later utilized to extract images containing built structures during compilation of  our main dataset for this project.

### Our Dataset
Due to the unavailability of any previous planned/unplanned localities dataset, we introduced our new dataset which contains high resolution satellite images of three major cities of Pakistan: Lahore, Peshawar and Hyderabad. Satellite images are downloaded using the Google Static Maps API, each with 256 x 256 pixels at zoom level 19, giving us a total of 140k satellite imagery. To only filter out the images containing buildings, we ultilized the building segmentation model trained on Village Finder dataset. The resulted images, which are filtered out from this step, are then tagged into multiple labels. For each image, we have three mandatory labels: layout, building and greenery density. Options for tagging building density are high building density (>80), moderate building density (50%-80%) and low building density (<50%). Similarly, greenery can be tagged out of dense greenery (>50%), sparse greenery (5-50%) and very sparse greenery (<5%). The layout of the images can be either regular or irregular. Additionally , we also have four optional labels including grass, trees, exposed soil and large buildings. In Fig. 3, we have shown some of the images of each city from our dataset.

## Building Segmentation

## Multi Task Learning

## Evaluating

## Conclusion

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/mominali12/Urban-Analysis-G2O/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mominali12/Urban-Analysis-G2O/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
