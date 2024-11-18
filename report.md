# AI Project 1 Report
## Group 39 - Denis Elshani - Thibaud Despriet

### Building the classifier
---

**Question 1 What challenging aspects do you anticipate in this dataset after exploring it?**

The Fashion MNIST dataset contains classes with similar visual features, such as "Shirt" and "T-shirt/top", which can be challenging for the model to differentiate. Additionally, variations in style, texture, and lighting conditions in the images may affect classification accuracy.

**Question 2 Which metric did you select for this task, and why?**

Accuracy was selected as the evaluation metric because the dataset is balanced across all classes, making accuracy a suitable measure of overall model performance.

**Question 3 Based on the training and validation curves from the history plot of your initial model,
what conclusions can you draw?**

The training and validation curves show that the model's accuracy improves over epochs without significant overfitting. The validation accuracy closely follows the training accuracy, indicating good generalization to unseen data.

**Question 4 Which hyperparameters did you optimize? Did you attempt all possible combinations
of parameter values (grid search) or optimize them one at a time? If you tuned the hyperparameters
sequentially, did you select the values to try upfront, or did you base them on the performance of
previous values? Please explain and motivate your strategy.**

Hyperparameters such as the number of filters in convolutional layers, learning rate, and batch size were optimized. They were tuned sequentially based on the performance observed after each training run. This approach allowed for adjusting one parameter at a time to isolate its effect on the model's performance.

**Question 5 Did the regularization scheme you tried help? Provide a possible explanation for it.**

Implementing dropout regularization helped reduce overfitting by randomly deactivating neurons during training. This prevented the model from becoming too dependent on specific neurons, improving its ability to generalize to new data.

**Question 6 For how many epochs have you trained the final model? How did you determine the
stopping criterion?**

The final model was trained for 30 epochs. The stopping criterion was determined using early stopping based on validation loss; training ceased when the validation loss stopped improving to prevent overfitting.

### Encoding the dataset
---

**Question 7 Select a validation sample and show its reconstructions when changing the latent space
sizes. Describe whether and how the reconstruction quality (as you perceive it) decreases with more
compression.**

![Validation Loss VS Latent Space Dimension](img/)

Latent space 32
![Latent space 32](img/latent_space_32.png)
Latent space 28
![Latent space 28](img/latent_space_28.png)
Latent space 24
![Latent space 24](img/latent_space_24.png)
Latent space 20
![Latent space 20](img/latent_space_20.png)
Latent space 16
![Latent space 16](img/latent_space_16.png)
Latent space 12
![Latent space 12](img/latent_space_12.png)
Latent space 8
![Latent space 8](img/latent_space_8.png)

As the latent space size decreases, the reconstruction quality diminishes noticeably. With larger latent space dimensions (e.g., 32), the autoencoder retains more detailed features of the original images, resulting in clearer and more accurate reconstructions. However, as the latent space is compressed to smaller dimensions like 16, 12, and down to 8, the reconstructions become progressively blurrier and lose finer details. This happens because a smaller latent space cannot capture all the essential information from the original data, leading to a loss of important features during the encoding process. Consequently, the autoencoder's ability to accurately reconstruct the original input deteriorates with increased compression.

**Question 8 Show a few representative examples of test inputs and their reconstructed images.
Comment on the visual quality of the reconstruction of the final autoencoder.**

![Original VS Reconstruction](img/reconstruction.png)

The reconstructed images maintain the overall structure and shape of the original inputs. Key features, such as the silhouette and primary distinguishing traits of the objects (e.g., bag handles, shoe outlines, and garment shapes), are well preserved. However, the reconstructions appear slightly blurred and lack finer details, suggesting that the autoencoder prioritizes capturing broad patterns over intricate textures. This indicates the model is effective in learning a compact representation of the input but struggles to perfectly replicate high-frequency details.

### Explaining the classifier
---

**Question 9 Considering the sources of misclassification, along with the performance of your model
on the training test dataset, explain the limitations of your model regarding data quality, overfitting,
and underfitting. Select four examples of misclassification that highlight these underlying issues and
plot them. Use local examples and counterexamples to illustrate your reasoning.**

<!-- TODO -->

### Use of generative AI and collaboration within the group

**Use of generative AI**

We occasionally utilized generative AI tools to assist with coding and debugging tasks. These tools provided helpful code suggestions and aided in resolving specific issues we encountered. While not a central part of our workflow, the AI assistance contributed to improving our efficiency in certain areas of the project.

**Collaboration and task distribution within the group**

Our collaboration was effective and well-organized. At the beginning of the project, Denis focused on building the classifier, while Thibaud worked on the autoencoder independently. After completing our respective tasks, we shared our findings and discussed the results to gain a comprehensive understanding of each component. We then worked together to explain the classifier, ensuring alignment on the project's objectives and outcomes. Before submitting the project, we jointly reviewed all aspects to verify correctness and enhance the overall quality, making necessary adjustments to improve our final submission.