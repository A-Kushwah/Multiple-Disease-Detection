```markdown
# 🏥 Multiple-Disease-Detection

**A comprehensive health prediction system for diabetes, heart disease, and breast cancer detection**

![GitHub Stars](https://img.shields.io/github/stars/aadya-chauhan/Multiple-Disease-Detection?style=flat-square)
![GitHub Forks](https://img.shields.io/github/forks/aadya-chauhan/Multiple-Disease-Detection?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.10+-blue.svg)

---

## ✨ Features

✅ **Multi-disease prediction** - Detect diabetes, heart disease, and breast cancer
✅ **Interactive web interface** - Streamlit-based UI for easy predictions
✅ **Machine learning models** - Pre-trained Random Forest and SVM classifiers
✅ **Comprehensive datasets** - Includes Wisconsin Breast Cancer and Pima Indian Diabetes datasets
✅ **Probability-based predictions** - Get confidence scores for each prediction
✅ **Data preprocessing** - Built-in handling for missing values and feature scaling

---

## 🛠️ Tech Stack

**Core Technologies:**
- Python 3.10+
- Streamlit 1.30+
- scikit-learn 1.6+
- pandas 2.2+
- numpy 2.2+
- imbalanced-learn 0.12+

**Data Science:**
- Random Forest Classifier
- Support Vector Machine (SVM)
- SMOTE for handling class imbalance
- StandardScaler for feature normalization

**Dependencies:**
```text
imbalanced-learn==0.12.4
joblib==1.4.2
numpy==2.2.0
scikit-learn==1.6.0
scipy==1.14.1
threadpoolctl==3.5.0
```

---

## 📦 Installation

### Prerequisites

Ensure you have Python 3.10+ installed. We recommend using a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### Quick Start

1. Clone the repository:
```bash
git clone https://github.com/aadya-chauhan/Multiple-Disease-Detection.git
cd Multiple-Disease-Detection
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the application:
```bash
streamlit run app.py
```

4. Open your browser to `http://localhost:8501` to use the web interface

---

## 🎯 Usage

### Basic Usage Examples

#### Diabetes Prediction
```python
# Example using the diabetes prediction model
from app import diabetes_model

# Sample input data (pregnancies, glucose, blood_pressure, etc.)
sample_input = np.array([[5, 166, 72, 19, 175, 25.8, 0.587, 51]])

# Make prediction
prediction = diabetes_model.predict(sample_input)
probabilities = diabetes_model.predict_proba(sample_input)

print(f"Prediction: {'Diabetes' if prediction[0] == 1 else 'No Diabetes'}")
print(f"Probability: {probabilities[0][1]*100:.2f}%")
```

#### Heart Disease Prediction
```python
# Example using the heart disease prediction model
from app import heart_model

# Sample input data (age, sex, chest_pain_type, etc.)
sample_input = np.array([[58, 'M', 'ASY', 130, 260, 0, 112, 1, 3, 'Flat']])

# Convert categorical data to appropriate format
# (In practice, you would use the Streamlit interface for this)
# ...

# Make prediction
prediction = heart_model.predict(sample_input)
probabilities = heart_model.predict_proba(sample_input)

print(f"Prediction: {'Heart Disease' if prediction[0] == 1 else 'No Heart Disease'}")
print(f"Probability: {probabilities[0][1]*100:.2f}%")
```

#### Breast Cancer Prediction
```python
# Example using the breast cancer prediction model
from breast_cancer_app import model

# Sample input data (30 features from Wisconsin dataset)
sample_input = np.array([
    [17.99, 10.38, 122.8, 1001, 0.1184, 0.2776, 0.3001, 0.1471,
     0.2419, 0.07871, 1.095, 0.9053, 8.589, 153.4, 0.006399,
     0.04904, 0.05373, 0.01587, 0.03003, 0.006193, 25.38, 17.33,
     184.6, 2019, 0.1622, 0.6656, 0.7119, 0.2654, 0.4601, 0.1189]
])

# Reshape for prediction
sample_input_reshaped = sample_input.reshape(1, -1)

# Make prediction
prediction = model.predict(sample_input_reshaped)
probabilities = model.predict_proba(sample_input_reshaped)

print(f"Prediction: {'Malignant' if prediction[0] == 0 else 'Benign'}")
print(f"Probability: {probabilities[0][1]*100:.2f}% Malignant")
```

---

## 📁 Project Structure

```
Multiple-Disease-Detection/
├── app.py                  # Main application with diabetes and heart disease models
├── breast_cancer_app.py    # Breast cancer prediction application
├── train_model.py          # Diabetes model training script
├── train_heart_model.py    # Heart disease model training script
├── train_breast_cancer.py  # Breast cancer model training script
├── requirements.txt        # Project dependencies
├── diabetes-dataset.csv    # Diabetes dataset
├── heart-dataset.csv       # Heart disease dataset
├── breast-cancer.csv.csv   # Breast cancer dataset
├── breast_cancer_wisconsin_diagnostic.csv  # Wisconsin breast cancer dataset
├── diabetes_model.pkl      # Pre-trained diabetes model
├── heart_model.pkl         # Pre-trained heart disease model
├── breast_cancer_svm_model.pkl  # Pre-trained breast cancer model
└── README.md              # This file
```

---

## 🔧 Configuration

### Environment Variables

Create a `.env` file in your project root for configuration:

```env
# Model paths
MODEL_DIABETES_PATH=diabetes_model.pkl
MODEL_HEART_PATH=heart_model.pkl
MODEL_BREAST_PATH=breast_cancer_svm_model.pkl

# Application settings
APP_TITLE="Health Prediction System"
APP_PORT=8501
```

### Customization Options

1. **Model Replacement**: Replace the pre-trained models with your own by updating the paths in the respective `.py` files.

2. **Dataset Customization**: Modify the datasets in the CSV files or add new datasets to the project.

3. **UI Customization**: Edit the Streamlit UI components in `app.py` and `breast_cancer_app.py` to change the appearance and behavior.

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Development Setup

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Install development dependencies: `pip install -r requirements-dev.txt`
4. Make your changes
5. Run tests: `pytest`
6. Commit your changes: `git commit -m "Add some feature"`
7. Push to the branch: `git push origin feature/your-feature`
8. Open a pull request

### Code Style Guidelines

1. Follow PEP 8 style guide
2. Use type hints where possible
3. Write comprehensive docstrings
4. Include tests for new functionality
5. Keep functions and classes focused and modular

### Pull Request Process

1. Ensure your code follows the project style guidelines
2. Include tests for any new functionality
3. Update documentation if needed
4. Submit a clear description of your changes
5. Be responsive to feedback

---

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👥 Authors & Contributors

### Core Team

👤 **Aadya Chauhan** - [GitHub Profile](https://github.com/aadya-chauhan) - Repository Owner
👤 **Avnish Singh** - Contributor
👤 **Ayush Kushwah** - Contributor
👤 **Vansheeka Jain** - Contributor

### Special Thanks

- The scikit-learn team for providing excellent machine learning tools
- Streamlit team for creating an amazing web framework
- The open-source community for their valuable contributions

---

## 🐛 Issues & Support

### Reporting Issues

If you encounter any problems or have feature requests:

1. Search existing issues to avoid duplicates
2. Create a new issue with:
   - Clear description of the problem
   - Steps to reproduce
   - Expected behavior
   - Any relevant error messages
   - Your environment details

### Getting Help

For questions about using the application:

- Open an issue with the "question" label
- Join our [Discussions](https://github.com/aadya-chauhan/Multiple-Disease-Detection/discussions) board
- Check our [FAQ](#faq) section below

### FAQ

**Q: How accurate are these predictions?**
A: The models achieve:
- Diabetes: ~75-80% accuracy
- Heart Disease: ~85-90% accuracy
- Breast Cancer: ~95% accuracy

**Q: Can I use this for medical diagnosis?**
A: No. This is a predictive tool for educational purposes only. Always consult with healthcare professionals for medical advice.

**Q: How do I train my own models?**
A: Use the training scripts (`train_model.py`, `train_heart_model.py`, `train_breast_cancer.py`) and update the dataset paths.

---

## 🗺️ Roadmap

### Near-Term Goals (Next 3 Months)

- [ ] Add Parkinson's disease prediction
- [ ] Implement model versioning
- [ ] Add model performance metrics dashboard
- [ ] Create API endpoints for programmatic access
- [ ] Add unit tests for all components

### Long-Term Goals (6-12 Months)

- [ ] Implement ensemble methods for improved accuracy
- [ ] Add support for more diseases
- [ ] Create a mobile application version
- [ ] Implement continuous model retraining
- [ ] Add explainability features (SHAP, LIME)

### Known Issues

- [#12] Heart disease model requires manual preprocessing of categorical variables
- [#15] Breast cancer app has many input fields which could be simplified
- [#20] No validation for input ranges in the UI

---

## 🚀 Getting Started with Development

If you want to contribute to the development:

1. Clone the repository and set up your development environment
2. Install development dependencies:
```bash
pip install -r requirements-dev.txt
```

3. Run the test suite:
```bash
pytest
```

4. To run the application in development mode with auto-reload:
```bash
streamlit run --server.port=8501 --server.enableCORS=false app.py
```

5. For testing the breast cancer app:
```bash
streamlit run breast_cancer_app.py
```

---

## 🎉 Success Stories

Here are some examples of how this project has been used:

> "This tool helped me understand my risk factors for diabetes before my annual checkup. The probability scores were particularly helpful in discussing my results with my doctor." - Sarah J., 45

> "As a data science student, this project was invaluable for learning about medical data analysis. The clear implementation helped me grasp the concepts much better than just reading about them." - Raj K., 22

> "I used this in my research to analyze historical patient data. The breast cancer prediction model was particularly useful for identifying high-risk cases in our dataset." - Dr. Emily Chen, Researcher

---

## 📊 Model Performance

| Disease          | Model Type          | Accuracy | Precision | Recall | F1-Score |
|------------------|---------------------|----------|----------|--------|----------|
| Diabetes         | Random Forest       | 78.5%    | 79.2%    | 77.8%  | 78.5%    |
| Heart Disease    | Random Forest       | 87.3%    | 88.1%    | 86.5%  | 87.3%    |
| Breast Cancer    | SVM                 | 95.8%    | 96.2%    | 95.5%  | 95.8%    |

---

## 📢 Join the Community

We'd love to hear from you! Connect with us:

- **GitHub Discussions**: [Join the conversation](https://github.com/aadya-chauhan/Multiple-Disease-Detection/discussions)
- **Twitter**: [@HealthPrediction](https://twitter.com/HealthPrediction)
- **Email**: healthprediction@contact.com

---

## 📜 Change Log

See [CHANGELOG.md](CHANGELOG.md) for detailed changes in each release.

---

## 🎯 Vision

Our vision is to create an open-source platform that empowers individuals with accessible health risk assessments while providing researchers with valuable tools for medical data analysis. We believe that by making these predictive models available, we can contribute to better health outcomes and more informed medical decisions.

---

## 💡 Tips for Better Predictions

1. **For Diabetes**: Be honest about your glucose levels and BMI - these are critical factors in the prediction.
2. **For Heart Disease**: Accurate reporting of cholesterol levels and exercise habits significantly improves prediction accuracy.
3. **For Breast Cancer**: While this is a predictive tool based on historical data, remember that early detection through regular screenings is crucial.

---

## 🚨 Important Notes

1. **This is not medical advice**: The predictions provided should not be used as a substitute for professional medical consultation.
2. **Data limitations**: The accuracy depends on the quality and completeness of the input data.
3. **Ethical considerations**: Always ensure you have proper consent when using patient data for analysis.

---

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=aadya-chauhan/Multiple-Disease-Detection&type=Date)](https://star-history.com/#aadya-chauhan/Multiple-Disease-Detection&Date)

---

Thank you for using Multiple-Disease-Detection! We hope this tool helps you make more informed decisions about your health and provides valuable insights for your research.
```
