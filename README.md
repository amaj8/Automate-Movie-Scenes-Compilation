# Automate-Movie-Scenes-Compilation
No need to spend hours to edit and clip movies to create a compilation of scenes of your favourite character. Automate this task using Python and Face Recognition!

## Inspiration
I wanted to compile all the scenes of Miss Lemon in Agatha Christie's Poirot (one of my favourite TV series). I decided to automate this task instead.

## What it does
Given a video file (of a movie or an episode of a series say) and an image of a character in the video, it outputs all the scenes where the character is present. 
Currently it does not distinguish whether the character is in focus or in the background.

## How I built it
I used the face_recognition library in Python to detect faces of the character in every frame. I then used the moviepy library to write all the frames with the character in a new video file. 

## Challenges I ran into
Face recognition on a normal laptop takes a long time (and might even crash your laptop if it's a large video file). For instance it took 6-7 mins to process a 26 sec video. 
Later I used frame resizing, threading (running a separate thread to fetch and then queue the frames of the video) and then the free GPU resources via Google colab to speed things up. Now a 24 min video is processed in 9-10 mins, which is significantly faster.

## Accomplishments that I'm proud of
* I could decrease the execution time significantly. 
* All scenes were captured correctly, even when the character wasn't in focus. 
* It only requires one image of the character
* Also, no training is required (since the CNNs in the face_recognition library are pretrained).

## What I learned
I learnt how to do face recognition using Python and how to edit videos using moviepy. I also learnt how to speed things by using GPUs.

## What's next for Automate Movie Scene Compilation
* Include the audio in the scenes
* Build a web app for users 
* Add more features such as recognising whether the character is in focus or not and whether the character speaks or not in the scene.
