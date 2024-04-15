## Overview

I created a prediction model for the nonprofit Alphabet Soup to help them determine which funding applicants would be most successful using 'IS_SUCCESSFUL' as my "success" target. In preprocessing we removed 'NAME' and 'EIN' columns and binned data from the rarer application types and classifications to determine the most common potential sources of success. Other features included: affiliation, organization, use case, status, income, requested donation amount, and if each potential donor had special considerations.

To achieve the target model performace we built our prediction model with two hidden 'relu' layers, the first comprised of 80 nodes and the second comprised of 30 with a single 'sigmoid' output layer. This model came in at about 0.7265 for accuracy with a rating of 0.5537 for loss. While accuracy and loss did minutely improve with each succeeding epoch, it is likely a model with more hidden layers might bring better results.

## Results

### First Prediction Model

Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense (Dense)               (None, 80)                3520      
                                                                 
 dense_1 (Dense)             (None, 30)                2430      
                                                                 
 dense_2 (Dense)             (None, 1)                 31        
                                                                 
=================================================================
Total params: 5981 (23.36 KB)
Trainable params: 5981 (23.36 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________

- Loss: 0.5537
- Accuracy: 0.7265

### Second Prediction Model

Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense (Dense)               (None, 80)                3520      
                                                                 
 dense_1 (Dense)             (None, 30)                2430      
                                                                 
 dense_2 (Dense)             (None, 15)                465       
                                                                 
 dense_3 (Dense)             (None, 1)                 16        
                                                                 
=================================================================
Total params: 6431 (25.12 KB)
Trainable params: 6431 (25.12 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________

Loss: 0.5557  
Accuracy: 0.7254 

### Third Prediction Model


Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense (Dense)               (None, 80)                3520      
                                                                 
 dense_1 (Dense)             (None, 30)                2430      
                                                                 
 dense_2 (Dense)             (None, 15)                465       
                                                                 
 dense_3 (Dense)             (None, 15)                240       
                                                                 
 dense_4 (Dense)             (None, 1)                 16        
                                                                 
=================================================================
Total params: 6671 (26.06 KB)
Trainable params: 6671 (26.06 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________

Loss: 0.5555 
Accuracy: 0.7261

## Summary

Our prediction model was a very "broad strokes" and did achieve a basic accuray of 0.72. With the addition of a third hidden layer, accuracy dropped to 0.7254 and with a fourth hidden layer we saw 0.7261 for accuracy but all results hovered in a similar range. If I were to run further tests I would try using fewer layers and nodes. I would also want to examine the data features more closely to see what factors produced the best results.