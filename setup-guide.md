# Setup & Installation Guide

## Quick Start for Beginners

This guide will help you set up Omni Flux Automation Engine from scratch. Don't worry - it's easier than it sounds!

---

## Step 1: Get a Google Gemini API Key (5 minutes)

### What is an API Key?
An API key is like a password that lets your notebook talk to Google's AI (Gemini).

### How to Get One:

1. **Go to Google AI Studio**
   - Open: https://aistudio.google.com/app/apikeys
   - Click **"Get API Key"** button
   - Click **"Create API Key"** in new project

2. **Copy Your API Key**
   - You'll see a long string of characters
   - Copy it (important!)
   - Don't share it with anyone

3. **Save It Safely**
   - Keep it in a text file
   - You'll need it in Step 3

---

## Step 2: Fork/Clone the Repository on GitHub

### For Beginners - Use GitHub's Fork Button (Easiest!)

1. **Go to the Project Repository**
   - Copy the GitHub URL

2. **Click the "Fork" Button**
   - Top right corner of the page
   - This creates YOUR copy of the project

3. **You now have your own copy!**
   - You can edit it without affecting the original
   - Located at: `github.com/YOUR_USERNAME/omni-flux-automation-engine`

### Alternative: Clone to Your Computer

```bash
# Open Command Prompt (Windows) or Terminal (Mac/Linux)
git clone https://github.com/YOUR_USERNAME/omni-flux-automation-engine.git
cd omni-flux-automation-engine
```

---

## Step 3: Set Up Your Kaggle Notebook

### Option A: Use Kaggle Directly (Recommended for Beginners)

1. **Go to Kaggle**
   - https://www.kaggle.com

2. **Upload the Notebook**
   - Click "Create" → "Notebook"
   - Paste your main code
   - Save

3. **Add Your API Key**
   - In first cell:
   ```python
   import os
   os.environ['GOOGLE_API_KEY'] = 'YOUR_API_KEY_HERE'
   ```

4. **Run the notebook!**
   - Click the play button for each cell

### Option B: Use Jupyter Locally

1. **Install Python** (if you don't have it)
   - Download from: https://www.python.org/downloads/
   - During installation, check "Add Python to PATH"

2. **Open Command Prompt/Terminal**

3. **Install Required Packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Start Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Open Your Notebook File**
   - It will open in your browser
   - Click on your `.ipynb` file

6. **Add Your API Key**
   - In the first cell:
   ```python
   import os
   os.environ['GOOGLE_API_KEY'] = 'YOUR_API_KEY_HERE'
   ```

---

## Step 4: Install Dependencies

### What are Dependencies?
Libraries and packages your code needs to run.

### How to Install:

**Method 1: Using requirements.txt (Easiest)**
```bash
pip install -r requirements.txt
```

This installs:
- `google-generativeai` (connects to Gemini)
- `python-dotenv` (manages API keys safely)
- `ipython` (better notebook experience)

**Method 2: Install Individually**
```bash
pip install google-generativeai
pip install python-dotenv
pip install ipython
```

---

## Step 5: Test the Setup

### Run This Test Code:

```python
# Test if everything is set up correctly
import os
from google import genai

# Check if API key is set
api_key = os.environ.get('GOOGLE_API_KEY')
if api_key:
    print("✅ API key found!")
else:
    print("❌ API key not found. Set it in the first cell.")

# Test Gemini connection
try:
    client = genai.Client(api_key=api_key)
    response = client.models.generate_content(
        model="gemini-2.0-flash",
        contents="Say 'Hello from Omni Flux!' briefly"
    )
    print(f"✅ Gemini connected! Response: {response.text}")
except Exception as e:
    print(f"❌ Error: {e}")
```

### Expected Output:
```
✅ API key found!
✅ Gemini connected! Response: Hello from Omni Flux!
```

---

## Step 6: Run Your First Query

### Example Code:

```python
# Test the agent system
query = "Improve my XGBoost model from 0.87 to 0.92 accuracy"

# Run through the system
response = test_agent(query)

# Print the response
print(response)
```

### What to Expect:
- Response from Coordinator Agent
- Routing decision
- Specialist agent output
- Formatted recommendations

---

## Troubleshooting

### Problem 1: "ModuleNotFoundError"
**Error Message**:
```
ModuleNotFoundError: No module named 'google'
```

**Solution**:
```bash
pip install google-generativeai
```

---

### Problem 2: "API Key Error"
**Error Message**:
```
Error: Invalid API key
```

**Solution**:
1. Check your API key is copied correctly
2. No spaces or quotes around the key
3. Re-generate a new key if unsure

---

### Problem 3: "Kaggle Notebook Not Running"
**Error Message**:
```
Timeout or kernel error
```

**Solution**:
1. Click "Restart Kernel"
2. Run cells one by one
3. Check for infinite loops

---

### Problem 4: "Import Errors"
**Error Message**:
```
ImportError: cannot import name 'X'
```

**Solution**:
1. Make sure you ran: `pip install -r requirements.txt`
2. Restart your notebook after installing
3. Check spelling of import statements

---

## Environment Variables (Optional but Recommended)

### Why Use Environment Variables?
- Safer (API key not in your code)
- Better for sharing code
- Professional practice

### How to Set Up:

**Step 1: Create `.env` file**
In your project folder, create a file named `.env`:
```
GOOGLE_API_KEY=your_api_key_here
```

**Step 2: Load in Your Code**
```python
from dotenv import load_dotenv
import os

load_dotenv()
api_key = os.getenv('GOOGLE_API_KEY')
```

**Step 3: Never Commit .env File**
Add to `.gitignore`:
```
.env
__pycache__/
*.pyc
```

---

## Directory Structure After Setup

Your folder should look like:

```
omni-flux-automation-engine/
├── main_notebook.ipynb              # Your main code
├── README.md                        # Project description
├── LICENSE                          # License file
├── requirements.txt                 # Dependencies
├── .env                             # API key (don't commit!)
├── .gitignore                       # Files to ignore
│
├── examples/                        # Demo files
│   ├── model-improvement-example.md
│   ├── debugging-example.md
│   └── strategy-example.md
│
├── docs/                            # Documentation
│   ├── architecture.md
│   ├── setup.md
│   └── troubleshooting.md
│
└── (your test files)
```

---

## Verify Installation Checklist

- [ ] Python 3.7+ installed
- [ ] `pip` working correctly
- [ ] Dependencies installed (`pip install -r requirements.txt`)
- [ ] Google Gemini API key obtained
- [ ] API key set in your notebook
- [ ] Test code runs successfully
- [ ] You see "✅" messages from test

---

## Next Steps

1. **Read the Documentation**
   - Start with: `docs/architecture.md`

2. **Try the Examples**
   - Run: `examples/model-improvement-example.md`

3. **Customize for Your Project**
   - Modify the system for your needs

4. **Push to GitHub**
   - Follow GitHub guide below

---

## How to Push Your Project to GitHub

### Step 1: Create a New Repository
1. Go to github.com
2. Click "+" → "New repository"
3. Name it: `omni-flux-automation-engine`
4. Click "Create repository"

### Step 2: Push Your Code
```bash
# Navigate to your project folder
cd your_project_folder

# Initialize git
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Omni Flux Automation Engine"

# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/omni-flux-automation-engine.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Verify on GitHub
- Go to your GitHub repository
- You should see all your files there!

---

## Getting Help

1. **Check Troubleshooting Section**
   - This document

2. **Check Architecture Docs**
   - `docs/architecture.md`

3. **Run Test Code**
   - See Step 5 above

4. **Check Example Files**
   - `examples/` folder

5. **Read Error Messages Carefully**
   - They usually tell you what's wrong!

---

## Common Questions

**Q: Do I need to pay for Gemini API?**
A: No! Google gives free tier with good limits.

**Q: Can I run this offline?**
A: No, you need internet for Gemini API.

**Q: Is my data private?**
A: Your queries go to Google but aren't stored long-term.

**Q: Can I modify the code?**
A: Yes! Fork it and make it your own.

**Q: How do I share my project?**
A: Push to GitHub and share the link!

---

## Success Indicators

If you see these, you're all set:
- ✅ No errors in notebook
- ✅ API key connects
- ✅ Test queries return responses
- ✅ Agents route correctly
- ✅ Logging works

---

**Congratulations!** You're ready to use Omni Flux! 🎉

For more help, check the troubleshooting guide or the architecture documentation.
