I am designing a semantic segmentation NN for autonomous vision on roads. Since I have a relatively small computational power and a small dataset (10.000 images) I decided to employ transfer learning

Architecture will be Fully connected Network rather than using dense layers. It uses the feature extractor layers of VGG16 than connects to FCN by building a U-Net like structure as follows (Initially I wanted to use U-net but not enough computational power :/);


### -->Encoder: VGG16 
Use the feature extractor layers:

Image_Input

Layer3

Layer4

Layer7

### -->Decoder: start at layer7 

layer8: 1x1 conv

layer9:  upsample to match layer4 of VGG16

*skip connection between VGG layer4 and layer9*

layer10:  upsample to match layer3 of VGG16

*skip connection between VGG layer3 and layer10*

layer11:  upsample to match input image
