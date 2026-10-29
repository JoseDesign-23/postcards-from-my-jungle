# Postcards from my Jungle

An imagined alien ocean made with generative models: sixteen aquatic specimens of an unknown world, each with an invented call and a phrase in a made-up language. The deeper a specimen floats on the map, the more dangerous it is.

**Live site:** https://josedesign-23.github.io/postcards-from-my-jungle/

## Training strategy

I trained a small diffusion model from scratch in Google Colab (free T4 GPU) using Hugging Face Diffusers: a U-Net that learns to remove noise. The dataset is a collection of real marine-animal photographs, `Ansh007/Jellyfish-Image-Dataset` (CC-BY-4.0). The small, briefly trained model produces creatures that resemble no Earth animal. Images were resized to 64 x 64 pixels, with a batch size of 16, a learning rate of 1e-4 and mixed precision. After a 2-epoch test I trained for 25 epochs (about 18 minutes), saving checkpoints to Google Drive.

## How the beasts were made

**Images:** I sampled 50 new specimens from random noise with the trained model, then chose the 16 strangest for the map. The rest are in `images/`.

**Sounds:** [confirm before submitting] I used the pre-trained Stable Audio Open 1.0 with text descriptions of sounds an alien deep-sea creature might make. The 16 clips have different durations, from about 3 to 15 seconds.

**Language:** I gave a language model a structured prompt asking for 16 phrases of two to four words, built from a small set of hyphenated syllables. The site shows no translations; the phrases, and the rotating planet facts at the bottom of the page, are written only in the invented language.

## How quality could improve

The images are small and blurry because the model is tiny and trained briefly. Better results would come from higher resolution, many more epochs, a larger and cleaner dataset, or fine-tuning a pre-trained image model instead of training from scratch. Sounds could improve with more careful prompts and several candidates per animal.

## AI assistance

I used Claude to help plan the project, write code and draft the animal language. [free / paid version: fill in]
