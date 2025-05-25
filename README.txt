# MNIST Digit Classification with CNN (PyTorch)

This project implements Convolutional Neural Networks (CNNs) for handwritten digit recognition using the MNIST dataset. It includes baseline training, architecture experimentation, hyperparameter tuning, and failure analysis — all using PyTorch.

---

## Project Structure

```

.
├── Q1\_BaselineCNN.py
├── Q2\_Variants/
│   ├── Variant1\_KernelSizes.py
│   ├── Variant2\_BatchNorm\_GAP.py
│   └── Variant3\_AdvancedComboCNN.py
├── Q3\_Hyperparameter\_Tuning.py
├── Q4\_BreakCNN/
│   ├── Fail\_HighLR.py
│   ├── Fail\_NoDropout.py
│   └── Fail\_BadInit.py
├── README.md
└── requirements.txt

````

---

##  Dataset

- **Name:** [MNIST Handwritten Digits](http://yann.lecun.com/exdb/mnist/)
- **Size:** 60,000 training + 10,000 test images (28×28 grayscale)

---

##  Installation & Usage

### Requirements

```bash
pip install torch torchvision matplotlib
````

### Running the Scripts

```bash
# Q1 - Baseline CNN
python Q1_BaselineCNN.py

# Q2 - Architectural Variants
python Q2_Variants/Variant1_KernelSizes.py
python Q2_Variants/Variant2_BatchNorm_GAP.py
python Q2_Variants/Variant3_AdvancedComboCNN.py

# Q3 - Hyperparameter Tuning
python Q3_Hyperparameter_Tuning.py

# Q4 - Failure Experiments
python Q4_BreakCNN/Fail_HighLR.py
python Q4_BreakCNN/Fail_NoDropout.py
python Q4_BreakCNN/Fail_BadInit.py
```

---

##  Task Summary

### Q1 – Baseline CNN

* 2 convolutional layers + MaxPool
* Fully connected → Dropout(0.5) → Output
* Optimizer: Adam, Learning rate: 0.001

### Q2 – Architectural Variants

* **Variant 1:** Different kernel sizes (5×5, 1×1)
* **Variant 2:** BatchNorm + LeakyReLU + Global Average Pooling
* **Variant 3:** Combined model (AdvancedComboCNN)

### Q3 – Hyperparameter Tuning

Tested the effect of:

* Learning Rate
* Optimizer (Adam vs SGD)
* Dropout Rate
* Batch Size
* Weight Initialization

**Best Configuration:**

* Architecture: AdvancedComboCNN
* Optimizer: Adam
* Learning Rate: 0.001
* Batch Size: 64
* Dropout: 0.5
* Initialization: He (Kaiming)

### Q4 – Try to Break the CNN

Deliberate model failures:

*  **Too high learning rate** → unstable training
*  **No dropout** → overfitting
*  **Bad initialization** → symmetry, no learning

---

##  Results

The best model achieved **over 98% test accuracy** with stable convergence and minimal overfitting. Each experiment includes training logs and accuracy/loss plots.

---

##  Author

Developed for a Machine Learning course assignment.
Student: *Mesut YILDIZ*
Institution: *Hacettepe University*

---

## 📄 License

This project is for academic use only.

```


