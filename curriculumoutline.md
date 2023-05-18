# Purpose of this doc
We're coming up with an outline of concepts, demos, and topics for a set of open modules on lo-fi machine learning

# Markov processes
## Core concepts
### Math introduced
 - probability
 - 
### Context vs. contextless
### Randomness for generation
## Demos
### Text generation
### Audio generation
### Absurd image gen
# Nearest neighbors and applications
## Core concepts
## Demos
### phone sensor lab
- Get pitch, yaw and roll from mobile phone via [sensors api](https://developer.mozilla.org/en-US/docs/Web/API/Sensor_APIs) (chrome-like browsers + safari)
- Create a data set of 3 classes (using phone, phone flat, phone in bags or pockets)
- Use kNN to see if our "shady app" can classify user "phone engagement" from background polling the position
- Discussion: "meaning" of data. does position really map to use?
### photo mosaic (with your own photos)
inspiration:
https://www.lambertleong.com/projects/photo-mosaic

can we let them link to a google drive folder in-browser to collage?
https://www.slidesmaker.me/blog/google-drive-api-javascript-all-operations

- have students take a photo of their own and collage it out of their other photos

art potential in very simple algorithms
### zany idea: finding the closest poetic match
Okay hear me out (and I might need to proof of concept this to demonstrate it's possible) consider adapting this algorithm
https://tug.org/docs/liang/liang-thesis.pdf
that's used for hyphenation to, instead, find and break down the syllabic structure of words

the learner is trained on a bunch of poetic forms and then matches the syllabic patterns to the one that's the closest fit, then forces the linebreaks so it kinda fits albeit probably with decent wrenching

No I'm not actually sure how this will work it just sounds fun and I want something textual
# Curve fitting: a first introduction
# Optimizing in 1-d: finding peaks and valleys
# Smoothness and gravity
Here's where we introduce baby's first automatic differentiation
(inspiration: https://thenumb.at/Autodiff/)

the goal isn't to teach calculus it's to build intuition for how it works, slopes, rates of change, &c.
## Slope of lines
## Everything is a line if you zoom in
## Finding the slopes automatically
## Multiple dimensions
## Demos


# When all you have is gravity, everything looks like a hill
# Optimizing: biologically inspired tricks
## Genetic algorithms
# Optimizing: neural networks
The point of this is that we can finally introduce the idea that neural networks are an easy way to turn things into "smooth" operations

