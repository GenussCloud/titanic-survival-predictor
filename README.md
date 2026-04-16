# Titanic Survival Prediction Website

A modern, interactive web application for predicting Titanic passenger survival using a trained Random Forest machine learning model.

## 📋 Features

- **Interactive Input Form**: Clean, intuitive interface for entering passenger information
- **Real-time Feedback**: Slider values update instantly as you adjust them
- **Feature Inputs**:
  - Passenger Class (1st, 2nd, 3rd)
  - Gender (Male, Female)
  - Age (0-80 years)
  - Siblings/Spouses aboard (0-8)
  - Parents/Children aboard (0-6)
  - Ticket Fare (£0-512)
  - Port of Embarkation (Southampton, Cherbourg, Queenstown)

- **Prediction Results**: 
  - Survival prediction (Would Survive / Would Not Survive)
  - Confidence probability (0-100%)
  - Visual probability bar

- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Professional UI**: Modern gradient design with Bootstrap styling

## 🚀 How to Use

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Local web server (required for loading JSON files via fetch)

### Setup Instructions

1. **Ensure all files are in the same directory**:
   ```
   MLOPs/
   ├── index.html
   ├── predict.js
   ├── titanic_random_forest_model.json
   └── README.md
   ```

2. **Start a local web server**:
   
   **Option A - Python 3**:
   ```bash
   cd /Users/fabian/SynologyDrive/5BHIF_WH/DSAI/MLOPs
   python -m http.server 8000
   ```
   
   **Option B - Python 2**:
   ```bash
   python -m SimpleHTTPServer 8000
   ```
   
   **Option C - Node.js**:
   ```bash
   npx http-server
   ```

3. **Open in browser**:
   - Navigate to `http://localhost:8000` (or as indicated by your server)
   - The page will load with the trained model

4. **Make a prediction**:
   - Fill in passenger details
   - Click "Calculate Prediction"
   - View the survival prediction result

## 📊 How Predictions Work

The prediction engine:

1. **Loads the trained model** (`titanic_random_forest_model.json`)
2. **Preprocesses input data**:
   - Standardises numeric features using training data statistics
   - One-hot encodes categorical features (Sex, Embarked)
3. **Applies the model**: Uses a Random Forest classification algorithm
4. **Returns probability**: Shows survival likelihood (0-100%)

### Feature Importance

The model considers these factors:
- **Gender**: Females had significantly higher survival rates ("women and children first")
- **Passenger Class**: 1st class passengers had better survival rates
- **Age**: Children had priority in evacuation
- **Fare**: Higher fares often indicated better accommodations
- **Family Size**: Traveling alone vs. in groups affected survival chances
- **Embarkation Port**: Subtle effect on outcomes

## 🎨 Design Features

- **Modern Interface**: Purple gradient background with clean card design
- **Real-time Updates**: Slider labels update as you adjust values
- **Interactive Feedback**: Buttons provide visual feedback on hover
- **Loading State**: Shows processing indicator during prediction
- **Error Handling**: Clear error messages for troubleshooting
- **Mobile Responsive**: Optimised for all screen sizes

## 📁 File Descriptions

### `index.html`
The main webpage containing:
- HTML form with input fields
- Bootstrap styling for responsive design
- Real-time slider value updates
- Result display container

### `predict.js`
JavaScript engine providing:
- Model loading via fetch API
- Feature preprocessing (standardisation, encoding)
- Prediction logic
- Results display and formatting

### `titanic_random_forest_model.json`
The exported machine learning model containing:
- Model metadata (type, hyperparameters)
- Feature names and types
- Preprocessing information
- Performance metrics
- Sample predictions

## 🔧 Technical Details

### Preprocessing Pipeline

**Numeric Features** (standardisation):
```
(value - mean) / standard_deviation
```

**Categorical Features** (one-hot encoding):
```
Sex: male=1/0, female=1/0
Embarked: C=1/0, Q=1/0, S=1/0
```

### Model Performance

Based on training data:
- **Test Accuracy**: 81.56%
- **F1-Score**: 0.7442
- **ROC-AUC**: 0.8294
- **Precision**: 0.7857
- **Recall**: 0.7111

## 🌐 Deployment

To deploy this website:

1. **Static Host** (GitHub Pages, Netlify, Vercel):
   - Upload all three files to your hosting service
   - Access via the provided URL

2. **Custom Server**:
   - Copy files to your web server root
   - Ensure CORS headers allow fetch requests

3. **Important**: Always use HTTPS in production environments

## 📝 Notes

- The model uses standardised training statistics for preprocessing
- Predictions are based on patterns learned from ~891 historical Titanic records
- Results are educational and approximate
- For production use, integrate with a backend server

## 🐛 Troubleshooting

### "Failed to load model" Error
- Ensure `titanic_random_forest_model.json` is in the same directory
- Check that your local web server is running
- Open browser developer console (F12) for detailed error messages

### Form validation fails
- All dropdown fields require a selection
- Check that your browser supports HTML5 form validation

### Predictions not changing
- Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- Reload the page (F5)
- Check browser console for JavaScript errors

## 📞 Support

For issues or improvements, check:
- Browser console (F12) for error messages
- Model JSON structure in your editor
- Local web server status

---

**Created**: April 2026  
**Model**: Random Forest Classifier (Titanic Survival Prediction)  
**Framework**: Vanilla JavaScript + Bootstrap CSS  
**Author**: ML Operations Student
