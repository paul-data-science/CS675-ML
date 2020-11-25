### GROUP 10 Project Type II
   ### Combining Supervised and Unsupervised Learning
   **by**</br>
   **Paul Aggarwal**</br>
   **Navneet Kala**</br>
   **Akash Shrivastava**</br>
   </br>
 **If this indeed how learning works in humans then the combination of unsupervised and super-
    vised learning may have a number of positive consequences such as:**
    
   **(i) faster training during supervision**
    
   **(ii) better generalization (i.e. performance on test set) or**
    
   **(iii) ability to achieve the same performance with ‘smaller’ models.**
    
   **The objective of the project will be to test this hypothesis using artificial neural networks (ANNs)
    for the supervised learning and autoencoders for the unsupervised learning.1 We will do that
    by first using autoencoders to obtain a small number of extra attributes. These attributes will be
    then fed to a standard ANN along with the original data.**
**This project has four files in following order:**

    (1) [CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-1-Selu-Sigmoid-BCE.ipynb]
    
    (2) [CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-2-Selu-Sigmoid-MSE.ipynb]
    
    (3) [CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-3-Selu-Softmax-BCE.ipynb]
    
    (4) [CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-4-Relu-Relu-MSE.ipynb]
**Overall observations using combinations of different dense layer activation and loss functions:**
    
   **Our main Unsupervised Stacked Autoencoder model (call it stacked_ae) uses Selu and Sigmoid activation functions with BinaryCrossEntropy loss function. It will make 29 new attributes (features) to be added to the MNIST data set. We will first perform training and testing of the combined 29 plus 784 features on our MLP supervised model called new_super_model. Then compare those results to the training and testing of only the original 784 features on our same MLP supervised model but call it just super_model. We tried different Stacked Autoencoder models consisting of different activation and loss functions which we compare to our final stacked_ae model below:**
    
   - **AE Model 2 using Sigmoid and MSE showed almost same visual degradation on decoding digits as shown on this page with stacked_ae model**
   **(refer to CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-2-Selu-Sigmoid-MSE.ipynb)**
    
   - **AE Model 3 using Softmax and Binary Cross Entropy showed most visual degradation on decoding digits (highest MSE loss number)**
   **(refer to CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-3-Selu-Softmax-BCE.ipynb)**
    
   - **AE Model 4 using Relu and MSE showed almost same visual degradation on decoding digits as shown on this page with stacked_ae model**
   **(refer to CS675-MNIST-PROJB-GROUP10-PAUL-AGGARWAL-AKASH-NAVNEET-4-Relu-Relu-MSE.ipynb)**
    
   **Our opinion is the Selu-Sigmoid-BinaryCrossEntropy functions of the stacked_ae model performed best. It visually shows better decoder digit output than Relu-Relu-MSE, Selu-Sigmoid-MSE and Selu-Softmax-BCE.**
   **(refer to cells 22 and 23 on this page for Selu-Sigmoid-BCE digits outputs.)**

### CONCLUSIONS</br>
 **Comparing the accuracies and losses between:**
   - **new_super_model (training and testing with new 29 features added to original 784 features)**
   - **super_model (training and testing with just original 784 features)**
   #### Really did not show significant difference between both accuracies (0.9749 vs 0.9727) but there's small difference between both losses (0.0854 vs 0.0984). So maybe adding the extra 29 features did slighlty improve the loss of our super_model. Please see training and testing with predictions (jump to cells 34 and 37).
