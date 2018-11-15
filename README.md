## Image and Text Embedding Exercises

This repository is a simple exercise to extract image and text feature using state-of-the-art image and text embedding models.

#Useful Articles:
[A Beginner's Guide To Understanding Convolutional Neural Networks](https://adeshpande3.github.io/adeshpande3.github.io/A-Beginner's-Guide-To-Understanding-Convolutional-Neural-Networks/) There are three articles in this series. Highly recommended.

#Requirements:
Ubuntu/MacOs
Keras
python
Tensorflow
Glove
numpy


#Data:
We will be using [Twitter malicious data](https://about.twitter.com/en_us/values/elections-integrity.html#data) for this exercise.

#Outputs:
1. twitter.txt: a list of twitter id.
2. twitter_tweets.txt: corredponding tweets to twitter.txt
2. twitter_img.npy: (N, 2048) vectors are the image features corresponding to twitter.txt
3. twitter_txt.npy: (N, 300) vectors are the text features corresponding to twitter.txt.

##Steps:

#Data Preparation:
1. Download tweet information the list of media archives from Internet Research Agency, and further download ira_tweet_media_hashed_1.zip. 
2. Extract all the files.
3. Create a list of twitter ids of the image files (please do not include vidoes or gifs) in ira_1, sort, and save it to twitter.txt.
4. Find the corresponding tweets in ira_tweets_csv_hashed file and save it to twitter_tweets.txt. (Make sure to read it with 'utf-8' encoding and save it with 'utf-8' encoding as well)

#Extracting Image Features
1. Load images, resize images to (224, 224, 3) (remain aspect ratio and pad white pixels if the original images are not square), and nomralize input vectors with preprocess_input function on Keras.
2. Use [ResNet-50](https://keras.io/applications/#resnet50) model (pretrained on ImageNet) to extract visual feature. You will get a 2048d vector for each image. (pooling = 'max') Save the feature vectors as twitter_img.npy.

#Extracting Text Features
1. Download word embedding model [Glove](https://nlp.stanford.edu/projects/glove/) which is pretrained on twitter data.
2. Text embedding will be the average of all word vectors in the tweets (ignore words that are not in the vocabulary).
3. Save the feature vectors as twitter_txt.npy. 
