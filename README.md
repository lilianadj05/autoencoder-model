# 🖼️ Autoencoder for Image Denoising

## 📌 Project Overview
This project focuses on building and evaluating an autoencoder model to denoise a dataset of pistachio images. An autoencoder is a type of neural network used for unsupervised learning of efficient data codings. In this case, the model is trained to reconstruct clean images from noisy versions, effectively learning to identify and remove noise.

## 📊 Dataset
The dataset consists of a collection of 600x600 pixel pistachio images. An exploratory data analysis (EDA) revealed that all images have a consistent aspect ratio of 1.0 (square) and uniform resolution. The pixel value distribution is symmetrical, peaking around a medium intensity, which indicates a balanced variation in lighting.

## 🔍 Key Findings
1. The baseline autoencoder model, despite its simple architecture, performed well, achieving an SSIM score of **0.8981** on the test set. This indicates a high level of structural similarity between the original and denoised images.
2. A modified model, developed through hyperparameter tuning with Keras Tuner, significantly improved performance. It achieved an SSIM score of **0.9581**, demonstrating that the fine-tuning process resulted in a more effective denoising model.
3. The training history of both models showed stable loss reduction with minimal gaps between training and validation loss, suggesting that the models generalized well without overfitting.
4. The visual output of the denoising process successfully removed the added noise, producing images that were nearly identical to the original clean images.

## 📈 Steps
1. **Data Cleaning & Preprocessing**: The images were resized to 100x100 pixels and normalized by scaling their pixel values from [0, 255] to [0, 1]. The dataset was then split into training (80%), validation (10%), and testing (10%) sets. Gaussian noise with a mean of 0.0 and a standard deviation of 0.1 was added to the training, validation, and test images to create the noisy input data for the model.
2. **Model Building & Training**:
   - **Baseline Model**: A simple convolutional autoencoder was built with an encoder-bottleneck-decoder structure and trained for 30 epochs using an Adam optimizer with mean_squared_error as the loss function.
   - **Modified Model**: Keras Tuner was used to find the best hyperparameters (number of filters, activation function, and learning rate). The best model was then retrained with the optimal configuration for 30 epochs.
3. **Evaluation**: The Structural Similarity Index Measure (SSIM) was used to quantitatively evaluate the models' performance on the test set, comparing the denoised images with the original clean images. The final denoising results were also visualized to qualitatively assess the effectiveness of the models.

## 💡 Conclusion
The project successfully demonstrated the effectiveness of a convolutional autoencoder for image denoising. The tuned model achieved excellent performance, as evidenced by a high SSIM score and visually impressive denoising results. The use of hyperparameter tuning was crucial in improving the model's ability to reconstruct the original image structure and details.

## 🔮 Possible Future Works
1. **Explore Different Noise Types**: Investigate how the model performs when trained on images with different types of noise, such as salt-and-pepper noise or speckle noise.
2. **Implement a Deeper Architecture**: Experiment with a deeper autoencoder or a U-Net architecture to see if it can further improve denoising performance, especially on more complex images or higher noise levels.
3. **Utilize an Attention Mechanism**: Integrate an attention mechanism within the autoencoder to allow the model to focus on the more important features of the image, potentially leading to better reconstruction of fine details.

## 👨‍💻 Author
**Liliana Djaja Witama** | Undergraduate Data Science Student at BINUS University
