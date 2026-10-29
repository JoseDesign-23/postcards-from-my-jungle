
**Live site:** https://josedesign-23.github.io/postcards-from-my-jungle/

## Training strategy

I ended up using the small diffusion model from Google Colab (free T4 GPU) using Hugging Face Diffusers, this allowed me to distort the dataset given and train briefly the model. The dataset is a collection of real marine-animal photographs, `Ansh007/Jellyfish-Image-Dataset` (CC-BY-4.0). Since small images are faster go to be used, and quality was not as necessary, I kept the images at 64x64 pixles, just enough to see an  image but not enough for a cleat view. The learning rate was of 1e-4 and mixed precision as it seemed to be the sweet spot to generate the images in a more structured way. Then, I went through a 2-epoch test so that i could see what would happen and then I trained for 25 epochs which took about 18 minutes, saving checkpoints to Google Drive.

## How the beasts were made

**Images:** I use the images from the dataset of jellyfish from Hugging Face. Sampled 50 new specimens to get the random noise with the trained model, then chose the 16 strangest for the map. The rest are in the images folder.

**Sounds:** I used the pre-trained Stable Audio Open 1.0 since it was already trained and with a large library of sounds. And then using text descriptions of sounds that could come from the ocean, such as crackles, bubbles, gulps or even a heartbeat, anytghing to give life to the sound without making the sound itself too obvious. Alos limited the duration of the sounds to 3.5 seconds to 15.

**Language:** I gave Claude (a language model) a structured prompt asking for 16 phrases of two to four words, specifically asking for a made-up language with no clear background or recognition. And so, the website itself is all written in the made-up language except on the instrctuctions, and I wanted also to have random facts of the new planet pop up but in the alien words.

## How quality could improve

Well, since the images are small and their quality isn't great, the main thing would be to maximize these characteristics in order to get better quality pictures. Also, training the diffusion model for a longer period of time and pass the images more, so more epochs. Maybe also providing more datasets of more animals, just to expand the training. 

## AI assistance

Claude: Free Plan: To help me in writing the codes and making more precise edits, and draft the animal language.
Hugging Face: Stability AI: Stable Audio Open: Free Plan
