---
title: "<img src='/images/portfolio_imgs/ml_music.jpg' width='25' height='25'>&nbsp;Machine Learning: Completing the Unfinished Bach Fugue"
excerpt: "Project work for the Machine Learning course offered under the MSc AI program at the University of Groningen"
collection: portfolio
---
---
[View Project on Github](https://github.com/v3rm1/ml_bach_fugue)

## Generating Bach's Last fugue

This repository contains code to predict Bach's last fugue using machine learning

The preprocessing folder contains converters to convert midi files to pitch list and pitch list back to midi. 
* It also has a converter for converting midi files to characters and can convert text back to midi.

The Simple Bigram folder contains the baseline bigram model. 
* Run simple_bigram.py to generate music using bigram model. 
* The txt_to_midi.py converts pitch text file to .midi file. 

* The DataScraping.ipynb script downloads midi files from a particular website. 
* CharNN.ipynb is the character level implementation of LSTM which trains on text characters converted from midi file.

You can listen to the generated output by playing bigram_output.mid.

 
If you want the trained embedding vectors you can get them [here](https://drive.google.com/file/d/1e3WbMZCvxr_OeTqtFZiuXrGYJqrGExqv/view?usp=sharing).

The predicted outputs are available in the Generated Music folder.