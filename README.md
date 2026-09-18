# 🤟 Sign Language Image Classifier

## 💼 Business use case

Static hand-shape recognition can support accessibility tools, learning applications, and gesture-based interfaces. This project focuses on recognizing the static-letter portion of American Sign Language from grayscale hand images, treating the problem as a 24-class classification task.

## 🎯 Principal objective

Transform tabular 28×28 image data into CNN-ready tensors and train a convolutional neural network that can distinguish unseen ASL hand signs. The notebook also provides a useful engineering lesson: a high headline accuracy does not remove the need to inspect the data pipeline and training diagnostics.

## 🔎 Summary of takeaways

The stored evaluation reports **97.17% test accuracy**, showing that the CNN learns strong class-specific visual patterns. At the same time, the notebook reveals issues that would need to be resolved before treating the model as production-ready: the pixel inspection contains `NaN` values, and the saved training history reports `NaN` validation loss.

Those details matter more than polishing the headline metric. I would first clean the invalid values, and add a confusion matrix plus per-class recall. The project is also intentionally narrower than full sign-language translation because dynamic letters and temporal context are outside the current dataset.

## 🧭 Explore the code

Review the [notebook](https://github.com/saels/sign-language-classifier/blob/9e0f37301a3090cd4090d3fdaf1834ba86e45953/Sign_language_classifier.ipynb) for the image reshaping pipeline, CNN architecture, training history, and test evaluation. The implementation is especially useful for seeing how model results and pipeline diagnostics should be assessed together rather than in isolation.
