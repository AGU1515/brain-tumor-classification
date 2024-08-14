# brain-tumor-classification
In certain instances, brain tumors can be fatal or severely damage quality of life by impairing one’s cognitive ability. Furthermore, their diagnosis process is flawed as it is tedious and prone to human error. Additionally, symptoms of the condition are hard to distinguish from other minor conditions, increasing diagnosis difficulty. Developing a tool for the early diagnosis of brain tumors is crucial, especially given that over 85,000 people in the US are diagnosed annually, with the potential for significant health impact. This paper proposes a transfer learning approach to solve this problem through the InceptionResNetV2 architecture, which served as the base architecture for the CNN used. The transfer learning model demonstrated strong performance, achieving an average accuracy, precision, recall, and f1-score of 95%, highlighting its potential as a reliable diagnostic tool. However, the model’s 6% false negative rate suggests that it is not suitable for use as a sole diagnosis tool but rather as a diagnostic aid to be used in conjunction with human verification. Integrating this diagnostic tool into medical practice could reduce the strain on medical professionals and accelerate the diagnostic process, leading to earlier detection and treatment of brain tumors. Future work should focus on enhancing the model’s precision to reduce false negatives and create tools to increase application potential that do things such as taking any MRI scan, diagnosing a tumor (with its grade), and predicting its progression. 

A dataset of about 3,000 images of 3 MRI scan types (sagittal, coronal, axial) and four different types of tumors (no tumor, meningioma tumor, pituitary tumor, glioma tumor). This project aimed to create a CNN to classify the tumors to try to make diagnosis of the condition easier. Initially, an ensemble learning approach (meaning using multiple models for one combined purpose). First, a scan classification model was used (see the cell titled "SCAN classification model") to classify images by the scan type which performed relatively well at a 94% accuracy. Then, the model would be passed to one of three models (AXModel, CORModel, SAGModel, depending on if the image was classified as an axial, coronal, or sagittal scan respectively) which classified the image into its tumor. These models performed quite poorly, as seen through the accuracies of the models (see "Create classification models for each scan - CNN"), the confusion matrixes (see "Confusion Matrixes"), the recall/precision (see "Recall/Precision"), and the ROC/AUC (see "ROC/AUC"). 

We realized the issue was that there wasn't enough data to take on such a nuanced approach with so many subsets - some categories were overly represented and the models consequently showed biases. Transfer Learning solves this issue by being pre-trained on datasets like the ImageNet dataset that optimizes the model's parameters and architecture for specific tasks. A transfer learning approach was taken using the InceptionResNetV2 model and achieved much better results as seen through the same metrics (see "InceptionResNetV2 Model"). 
