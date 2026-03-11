## Task 1: Food Identification with Segmentation

**Background**

Image segmentation models such as DeepLab and SAM models have been studied for food semantic segmentation for a decade. An experiment by Alahmari reveals that fine-tuning the Segment Anything (SAM) model with Low-Rank Adaptation (LoRA) layers increased accuracy by approximately 2% compared to DeepLabV3+ for binary segmentation (food vs. non-food) [1]. In another study by Lan, the proposed FoodSAM model enhance the accuracy around 1% compared to DeepLabV3+ [2]. Considering computational resources and performance, DeepLabV3 is selected for this experiment as the similarly of architecture with DeepLabV3+ and has been pre-trained on the COCO dataset, which includes food data. Another challenge in the FoodSeg103 dataset is the class imbalance. In this experiment, the performance of model using standard cross-entropy loss function, dice loss [3], and a hybrid approach which proposed for addressing class imbalance [4], [5] are compared to investigate the effectiveness of class imbalance handling.

**Conclusion**

The findings highlight that the choice of model backbone and loss function plays a crucial role in optimizing model fine-tuning, particularly for handling class imbalance in multi-class image segmentation. To improve the model’s performance, training the model with more dataset like FoodSeg154, UECFood and UECFoodComp could improve the generalization of the model, resulting in higher mIoU score.

## Task 2: Multimodal Idiomaticity Representation

**Background**

This study aims to investigate the impact of data augmentation and model architectures for multimodal idiomaticity representation. Data augmentation is the crucial process to improve the training result, in this study, Named Entity Recognition (NER) was applied to enhance text diversity before augmenting text with large language model [6]. To compare the zero-shot learning and fine-tuning, Contrastive Language-Image Pretraining (CLIP) was employed. Since, it has been trained on a large dataset, users able to leverage the model without fine-tuning and able to improve performance in specific task by fine-tuning [7], [8]. Furthermore, the combination of ViT and T5 models was integrated using late fusion to develop a multimodal model and compared with CLIP model, where features from text and image are extracted independently before being combined at a later stage for classification [7], [9].

**Conclusion**

In conclusion, fine-tuning CLIP with augmented data significantly improves performance. Data imbalance is less critical for fine-tuning when the dataset is sufficiently large. However, the consistency of test scores across models with low validation accuracy suggests that the test set may be too easy. Expanding the test set with more diverse idioms and balancing the distribution between train and test data could improve evaluation reliability. Additionally, incorporating more data could further enhance the model’s robustness and generalization in future work.

**References**
- [1]	S. S. Alahmari, M. Gardner, and T. Salem, “Segment Anything in Food Images.”
- [2]	X. Lan et al., “FoodSAM: Any Food Segmentation,” Aug. 2023, doi: 10.1109/TMM.2023.3330047.
- [3]	“shuaizzZ/Dice-Loss-PyTorch: implementation of the Dice Loss in PyTorch.” Accessed: Mar. 27, 2025. [Online]. Available: https://github.com/shuaizzZ/Dice-Loss-PyTorch/tree/master
- [4]	C. H. Sudre, W. Li, T. Vercauteren, S. Ourselin, and M. J. Cardoso, “Generalised Dice overlap as a deep learning loss function for highly unbalanced segmentations,” Jul. 2017, doi: 10.1007/978-3-319-67558-9_28.
- [5]	D. Huang, M. Wang, L. Zhang, H. Li, M. Ye, and A. Li, “Learning rich features with hybrid loss for brain tumor segmentation,” BMC Med Inform Decis Mak, vol. 21, Jul. 2021, doi: 10.1186/s12911-021-01431-y.
- [6]	X. Hu et al., “Entity-to-Text based Data Augmentation for various Named Entity Recognition Tasks,” Oct. 2022, [Online]. Available: http://arxiv.org/abs/2210.10343
- [7]	“Understanding OpenAI’s CLIP model | by Szymon Palucha | Medium.” Accessed: Mar. 28, 2025. [Online]. Available: https://medium.com/@paluchasz/understanding-openais-clip-model-6b52bade3fa3
- [8]	A. Radford et al., “Learning Transferable Visual Models From Natural Language Supervision,” Feb. 2021, [Online]. Available: http://arxiv.org/abs/2103.00020
- [9]	“Multimodal Models and Fusion - A Complete Guide | Medium.” Accessed: Mar. 28, 2025. [Online]. Available: https://medium.com/@raj.pulapakura/multimodal-models-and-fusion-a-complete-guide-225ca91f6861



