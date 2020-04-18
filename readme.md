This is the file for the Colab EVA4S4 notebook. 
MNIST dataset
Architecture
convolution set 1 
           convolution layer of 3X3 (1 to 16 channels) followed by drop layer ; #input = 28X28X1 OUtput: 26X26X16 RF 3X3
           followed by 3X3 (16 to 32 channels)  followed by drop layer ; #input 26X26X16 OUtput: 24X24X32 RF 5X5
           followed by maxpool    ; #input 24X24X32 o/p 12X12X32 RF 10X10
           
Second conv set ;  conv layer reduce to 8 channels using 1X1 conv followed by drop layer  ; #input 12X12X32 OUtput: 12X12X8 RF 10X10 
                  followed by 3X3 to 16 channels with padding followed by drop layer ; #input 12X12X8 OUtput: 12X12X16 RF 12X12 
                  followed by 3X3 to 32 channels followed by drop layer ;  #input 12X12X16 OUtput: 10X10X32 RF 14X14
                  followed by max pool ; #input 10X10X32 OUtput: 5X5X32 RF 28X28 
                  
 Third conv set
              conv layer reduce to 16 channels using 1X1 conv followed by drop layer ; #input 5X5X32 OUtput: 5X5X16 RF 28X28 
              conv layer reduce to 16 channels using 1X1 conv follwoed by drop layer ; #input 5X5X32 OUtput: 5X5X16 RF 28X28 
              followed by conv layer to  32 channels using 3X3 kernel  ; #input 5X5X16 OUtput: 3X3X32 RF 30X30 
              then reduce the 32 channels to 10 channels using a 3X3 conv. #input 3X3X32 output 3X3X10 
              Then gap layer top average using AdaptiveAvgPool2d
              
   tried batchnorm also, this reduced accuracy.
   Also tried SGD with various learning rates and momentum
   
   final model contains Adam Optimiser 
   
              
  
  
              
              
                  
