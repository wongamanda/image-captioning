# Image Captioning with Azure ML
A deep learning model to generate captions for Flickr images
	
### Project Goals: 
* Generate automatic descriptive captions for images
* Gain experience with RNN models

### Design Project Plan
**Objectives**:
* Build a supervised deep learning model that can create alt-text captions for images
	
**Define Output and success metric**:
* Generate a short caption for new images 
* Relatively high accuracy rate in predicting captions for images
			
**Data Access and description**: 
* [Flickr30k dataset](https://www.kaggle.com/atulyaatul1999/image-captioning-flicker-30k) (hosted on Kaggle) with roughly 30k images in JPEG format with over 158k captions. It has not been split into pre-defined training and test sets. 
* There are 5 different captions for the same image
		
**Modeling technique**:
* Base model VGG on the features of photos in the training set
* RNN or Transformer model - sequencing over natural-language image captions
	
**Execution stages**:
 1) Prepare data
    1) Download and store the .csv files in blob storage
    2) Clean captions data
    3) Build a list of images and corresponding captions (i.e., image-input and text-output)
    4) Split data into training and validation sets
2) Create vocabulary from the training dataset
    1) Preprocess captions
    2) Get unique words from all image captions
    3) Load pretrained word embeddings (GloVe)
    4) Tokenize captions into Tensorflow records
3) Use images to train a model
    1) Get data from blob storage
    2) Pass images as vectors through the RNN Decoder
4) Predict captions using trained model
5) Test model on validation data and measure accuracy

			
**Software Frameworks**:
* Python
* Tensorflow
* GloVe

