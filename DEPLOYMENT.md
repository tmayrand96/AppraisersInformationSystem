# 🚀 Deployment Guide for Streamlit Cloud

## 📋 Essential Files for GitHub Repository

Your GitHub repository should contain these **essential files**:

### ✅ **Required Files:**
1. **`streamlit_property_valuation_quantile.py`** - Main application
2. **`donnees_BDF.csv`** - Training dataset
3. **`requirements.txt`** - Python dependencies
4. **`.streamlit/config.toml`** - Streamlit configuration
5. **`README.md`** - Project documentation
6. **`.gitignore`** - Git ignore rules

### ❌ **Files to Exclude:**
- `venv/` directory
- `__pycache__/` directories
- `*.pyc` files
- Large model files (`.joblib`, `.pkl`) - they will be generated on first run
- IDE-specific files (`.vscode/`, `.idea/`)

## 🔧 Streamlit Cloud Deployment Steps

### 1. **Prepare Your Repository**
```bash
# Ensure you have these files in your repo root:
ls -la
# Should show:
# streamlit_property_valuation_quantile.py
# donnees_BDF.csv
# requirements.txt
# .streamlit/config.toml
# README.md
# .gitignore
```

### 2. **Push to GitHub**
```bash
git add .
git commit -m "Add property valuation app for Streamlit Cloud"
git push origin main
```

### 3. **Deploy on Streamlit Cloud**
1. Go to [share.streamlit.io](https://share.streamlit.io)
2. Sign in with GitHub
3. Click "New app"
4. Select your repository
5. Set **Main file path**: `streamlit_property_valuation_quantile.py`
6. Click "Deploy"

### 4. **First Run Setup**
- The app will automatically install dependencies
- Users will need to train the model first (go to "Model Performance")
- Models will be saved and reused for subsequent predictions

## 🎯 Repository Structure

```
your-repo/
├── streamlit_property_valuation_quantile.py  # ← Main app
├── donnees_BDF.csv                          # ← Training data
├── requirements.txt                          # ← Dependencies
├── .streamlit/
│   └── config.toml                          # ← Streamlit config
├── README.md                                # ← Documentation
├── .gitignore                               # ← Git ignore
└── DEPLOYMENT.md                            # ← This file
```

## ⚠️ Important Notes

1. **Model Files**: Don't include `.joblib` files in your repo - they'll be generated on first run
2. **Data File**: Make sure `donnees_BDF.csv` is included
3. **Dependencies**: All required packages are in `requirements.txt`
4. **Configuration**: `.streamlit/config.toml` ensures proper deployment settings

## 🔍 Troubleshooting

### Common Issues:
- **"Module not found"**: Check `requirements.txt` includes all dependencies
- **"File not found"**: Ensure `donnees_BDF.csv` is in the repository
- **"Model not trained"**: Users must train models on first use

### Performance Tips:
- Models are trained once and cached
- Subsequent predictions are fast
- Consider adding model files to repo if training takes too long

## 📞 Support

If you encounter issues:
1. Check the Streamlit Cloud logs
2. Verify all required files are present
3. Ensure dependencies are correctly specified
4. Test locally before deploying 