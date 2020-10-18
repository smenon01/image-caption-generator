# Image Caption Generator
S-89A Deep Learning for Natural Language Processing

### Problem Statement
Use deep learning and natural language processing techniques to generate relevant captions from input images.

### Approach
Trained a neural network with the Flickr 8k dataset, that takes an image and text input and produces an appropriate word sequence to describe the image. 

### Use / Benefits:
This process could be used to extract insights/summaries from images, provide image information to those with visual impairments, and to classify/identify patterns in social media photo albums (i.e. facial recognition), or perhaps even in medical imaging assessments. 

### Data Source:
The Flickr 8k dataset consists of around 8000 images (of everyday people and situations from Flickr) with five associated captions per image, with predefined training, validation, and test sets. 
-	Officially request data here: https://forms.illinois.edu/sec/1713398

### Drawbacks / Challenges:
-	There was necessary text and image preparation and heavy reliance on pretrained networks for extracting image features and representing words as vectors. 
-	Encountered overfitting (perhaps due to needing more data for training) despite applying regularization techniques and simplifying the network.  
-	The model’s effectiveness is limited to the variety of images it is trained on. 

### Results:
We were able to get the validation loss of generating sequences similar to actual captions to around 3.2, but experienced overfitting. The corpus BLEU scores used to evaluate the model were not high, but conducting predictions on test images (using both greedy and beam searches) resulted in captions that generally effectively capture the context of the images. Training with larger samples or employing data augmentation, as well as including an attention mechanism, cross-validation, and further hyperparameter tuning may improve results. 

### Working Example Description: 
The following notebooks were used to create the demonstration: 
1.	*project_img-features.ipynb*: Processes the dataset images in a pretrained convolutional neural network (CNN) and extracts/saves image features
2.	*model_create.ipynb*: Processes and visualizes dataset captions; creates training, validation, test data; tokenizes words and establishes word embedding; trains a “merge” model with a data generator; visualizes losses; evaluates model with BLEU scores; demonstrates a few examples of captions using greedy and beam searches.
3.	*model_demo.ipynb*: Loads final model and generates captions for a few random test images with image plotting. 

