# Music_Segmentation
Extracting drums , vocals , bass, others . 
Built an U-Net architecture with 3 encoder layers each containing Residual Block with 2 Convolution layers (using 3*3 filters)+ MaxPooling and 3 decoder layers to reconstruct the 4 stems.
Trained on musdb18 dataset (150 songs) among which 100 for training and 50 for test.
