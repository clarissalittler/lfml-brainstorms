# Pupose of this doc
An outline of the topics covered in AIML for the Arts (MUC 250) to identify what can be incorporated from the course as it has been, and what topics aren't possible in "lfml."

# Readings
- Chapters 1-3 "You Look Like A Thing and I Love You"
- Sea of Data: Apophenia and Pattern Recognition - Hito Steyerl
- Politics of Visibilty - Ramon Amaro

# Frame supervised vs unsupervised vs other types of learning
data and labels
unsupervised and reinforcement are covered in the current reading material but we don't really engage them (yet?)

# What is a model
Discussion of inputs and outputs re: data and labels
Vocab "dimensions"

# Classification vs Regression
Identify the differences between classification and regression 
Discrete categories vs continuous values
Thresholding continuous values to create discrete categories
Applications: what are the uses of each for real time interaction

## kNN Lab
- Get pitch, yaw and roll from mobile phone via OSC app
- Create a data set of 3 classes (using phone, phone flat, phone in bags or pockets)
- Use kNN to see if our "shady app" can classify user "phone engagement" from background polling the position
- Discussion: "meaning" of data. does position really map to use?

## Regression Lab
- discuss the shapes of functions ie "linear" vs "non linear"
- compare map() style functions to regression
- look at complexity (kinda likened to changing directions) for higher order polynomials
- plot points and try to get good matches
- introduce over/under fitting

## DTW, MFCC, Speech/Sound Classification
- "signals" as data, try to visualize a "time series"
- try to define "gestures" broadly to include speech
- problematize gestures (different speeds, different bodies, saying a word twice exactly the same)
- vocab/discuss "dimensionality reduction" and "feature extraction"
- max patch (provided) performs fft -> mfcc, assists creating dataset
- try to succesfully recognize a few words
- try to animate an anime character's mouth with phonemes and different images

## Neural Networks
(mainly just brought up to get a picture, we don't go into too much detail)
- use mnist problem and visualizing hidden layers to talk about weights in regards to image processing
- multiplying two images (masking)
- videos (3blue1brown neural networks first two)
- looking inside a neural network (ml4a github)
- use a "downsampled" web cam (12x16 rectangles/"pixels") to do image classifying
- thresholding outputs
- use confidence scores and thresholded outputs to control stuff

## Markov Chains
- randomness -> probability, like filtering or guiding a path
- vocab: probability distributions (and messing with/generating them)
- "look up tables"
- use a max patch to model midi files from the web
- combining markov models of different files
- discuss: limitations, higher "order" models, modeling with re to time, what happens to the markov model, cool connections to RNN, LSTM

# Second Half of Class (obsolete, f*** paywalls)
## RunwayML
- collection of RunwayML model interfaces
- segmentation
- deep fakes (first order motion model)
- pose estimation
- image generation
## Finding Data on the web
- crawling
- compiled data sets
- internet overview (DNS, HTTP, APIs)
- "renegade methods"



