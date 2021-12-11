# Jazz Generation using GANs

In this project, we aim to generate new music, primarily jazz and piano music, using generative adversarial networks, or GANs, by training such models on samples of authentic jazz and piano music found online. Prior to the use of GANs, autoregressive models like WaveNet were the main types of models used to produce music due to the sequential nature of audio data. However, autoregressive models suffer from slow sampling speeds and struggle to identify global structures in training data. Using GANs to generate music with appropriate computational representation should capture both global structure and local coherence while taking advantage of efficient sampling compared with autoregressive models. The representation of audio files as inputs to the models is challenging and poses obstacles in training and generation if that representation is too simple or complex. 

Code adapted from https://github.com/Ipsedo/MusicGAN

## Installation instructions

1. clone or download and extract the repository

2. Change to the base directory ./MusicGAN

3. Set up the conda environment by running the following command. This will create an environment called `musicgan`
 
`conda env create --file enviornment.yml`

4. Activate your environment by running

`conda activate musicgan`

5. It is now possible to either generate samples, train on a new dataset, or run the notebooks in

## How to

#### Generate samples

A pretrained model has been provided, you can generate samples from this model using this command. 

WARNING: The samples are quite loud so make sure to turn down your volume before playing

`python generate.py --gen_dict_state ./checkpoints/gen.pt --rand_channel 96 --nb_vec 1 --nb_music 5 -o ./gen_out`

#### Preprocess Data

You can preprocess your own raw audio data for training using the following command. Note that audio files need to be in .wav format

`python create_dataset.py -i ./path/to/audio.wav -o ./data`

#### Train Model

Once you have preprocessed data, you can begin training the model with the command below.

`python train.py -i ./data/ -o ./output RUN_NAME=MusicGAN`

#### Generate Magnatide and Phase Graphs

Running the `View Magnatude and Phase.ipynb` notebook and changing the filepath to your .wav file 




