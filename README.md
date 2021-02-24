# CViT
### Deepfake Video Detection Using Convolutional Vision Transformer

Implementation code for our paper. 
[link to paper](https://arxiv.org/abs/2102.11126)

### Requirements:
* Pytorch 1.4

### DL library used for face extraction
   * helpers_read_video_1.py
   * helpers_face_extract_1.py
   * blazeface.py
   * blazeface.pth

### Weights
1. cvit_nov16_Auged_90p_50ep.pth <br/>
   CViT model weight, November 16, 2020, Augmentation=90%, Epoch=50.

2. Deepfake_Oct6_Auged_90p_50ep.pth <br/>
   Deep CNN Deepfake detection weight - ~87% accuracy on DFDC dataset (not documented in the thesis)

### Preprocessing
extractfaces.py<br />
&nbsp;&nbsp;&nbsp;Face extraction from video. <br /> 
&nbsp;&nbsp;&nbsp;The code works for DFDC dataset. You can test it using the sample data provided. 

#### Predict CViT 

python cvit_prediction.py <br />
&nbsp;&nbsp;&nbsp; Predicts whether a video is Deepfake or not.<br />
&nbsp;&nbsp;&nbsp; Prediction value <0.5 - REAL <br />
&nbsp;&nbsp;&nbsp; Prediction value >=5  - FAKE


### Train CViT
To train the model on your own you can use the following parameters:<br />
&nbsp;&nbsp;e: epoch <br/>
&nbsp;&nbsp;s: session - GPU or TPU <br/>
&nbsp;&nbsp;w: weight decay  default= 0.0000001 <br/>
&nbsp;&nbsp;l: learning rate defualt=0.001 <br/>
&nbsp;&nbsp;d: path file <br/>
&nbsp;&nbsp;b: batch size, defualt=32 <br/>

python cvit_train.py -e 10 -s 'g' -l 0.0001 -w 0.0000001 -d sample_train_data/

### Authors
**Deressa Wodajo**<br />
**Solomon Atnafu (PhD)

### References
Deressa Wodajo and Solomon Atnafu, "[Deepfake Video Detection Using Convolutional Vision Transformer](https://arxiv.org/abs/2102.11126)," arXiv preprints arXiv:2102.11126, 2021. 
