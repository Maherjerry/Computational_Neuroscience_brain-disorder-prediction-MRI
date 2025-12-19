# Step 1: Explore Your OASIS-1 Data Structure
## 🎓 Educational Guide - Learn as You Go!

---

## 🎯 What is This Step About?

**Goal**: Before writing any code, we need to understand:
- What files we have
- How they're organized
- What information is in them
- What format the data is in

**Why this matters**: You can't write code to process data if you don't know what the data looks like!

**Time needed**: 15-20 minutes

---

## 📚 Background Knowledge

### What is OASIS-1?
- **OASIS** = Open Access Series of Imaging Studies
- **OASIS-1** = First version, contains brain MRI scans
- **Purpose**: Study brain structure in healthy people vs people with Alzheimer's disease
- **Your data**: 36 subjects with brain scans + information about each person

### What is an MRI Scan?
- **MRI** = Magnetic Resonance Imaging
- **What it shows**: Detailed pictures of brain structure (like a 3D photograph)
- **Why we use it**: Brain structure changes in Alzheimer's disease - we can see these changes in MRI scans
- **Format**: Your scans are in `.hdr` and `.img` format (this is an old but common format)

---

## 🔍 Step 1A: Explore Subject Folders

### What You're Looking For

Each person (subject) in the study has their own folder containing their brain scan.

### Action: Navigate to the Data Folder

**Path to go to**:
```
data/oasis_cross-sectional_disc12/disc12/
```

**What you should see**:
- Multiple folders, each named like: `OAS1_0001_MR1`, `OAS1_0002_MR1`, etc.
- **OAS1** = OASIS-1 dataset
- **0001, 0002** = Subject numbers
- **MR1** = First MRI scan session

### Action: Open One Subject Folder

Pick any folder (like `OAS1_0001_MR1`) and open it.

**What's inside?** You should see several files:

#### 1. `.hdr` File (Header File)
- **What it is**: Contains metadata about the scan
  - Image dimensions (width, height, depth)
  - Voxel size (size of each 3D pixel)
  - Orientation information
  - Data type
- **Why it matters**: Tells software how to read the image data
- **Think of it like**: The "instructions" for reading the image

#### 2. `.img` File (Image File)
- **What it is**: The actual brain scan data (the image itself)
- **Size**: Usually 5-20 MB per scan
- **Format**: Raw 3D image data
- **Why it matters**: This is the actual brain scan we'll analyze
- **Think of it like**: The actual photograph (but in 3D!)

**Note**: `.hdr` and `.img` files always come in pairs - you need both!

#### 3. `.txt` File (Text Metadata)
- **What it is**: Plain text file with scan information
- **Contains**: Scan date, scanner settings, etc.
- **Why it matters**: Useful for understanding scan quality
- **You can open it**: Just double-click to read it

#### 4. `.xml` File (XML Metadata)
- **What it is**: Structured metadata in XML format
- **Contains**: More detailed scan information
- **Why it matters**: Some software uses this for automatic processing
- **Note**: XML is a structured data format (like HTML but for data)

#### 5. `.gif` File (Preview Image)
- **What it is**: A 2D preview/snapshot of the brain scan
- **Why it's useful**: Quick way to see the brain without special software
- **Try this**: Double-click to open it - you should see a brain image!

### 🎓 Learning Checkpoint

**Questions to answer**:
1. How many subject folders do you see?
2. Can you open a `.gif` file and see a brain image?
3. Do you see both `.hdr` and `.img` files in each folder?

---

## 📊 Step 1B: Explore the Metadata File

### What is Metadata?

**Metadata** = Data about the data
- The brain scans are the **data**
- Information like age, diagnosis, test scores = **metadata**

### Action: Open the Excel File

**File location**:
```
data/oasis_cross-sectional.xlsx
```

**How to open**: Double-click the file (opens in Excel or similar program)

### What You'll See: Columns Explained

The Excel file has information about ALL subjects (even ones you don't have scans for). Here's what each column means:

#### Key Columns to Understand:

1. **ID** or **Subject ID**
   - Unique identifier for each person
   - Format: OAS1_XXXX (matches folder names)

2. **Age**
   - Person's age in years
   - **Why important**: Age affects brain structure (older = different brain)

3. **Gender** (M/F)
   - Male or Female
   - **Why important**: Brain structure differs slightly by gender

4. **Education**
   - Years of education
   - **Why important**: Education level can affect cognitive test scores

5. **SES** (Socioeconomic Status)
   - Social/economic background
   - **Why important**: Can affect health outcomes

6. **MMSE** (Mini-Mental State Examination)
   - **What it is**: Cognitive test (tests memory, attention, etc.)
   - **Score range**: 0-30
   - **Higher score** = Better cognitive function
   - **Why important**: Measures how well the brain is working
   - **Example**: Score of 25+ = normal, Score below 20 = possible dementia

7. **CDR** (Clinical Dementia Rating)
   - **What it is**: Rating of dementia severity
   - **Values**: 0, 0.5, 1, 2, 3
   - **0** = No dementia (healthy)
   - **0.5** = Very mild/uncertain
   - **1** = Mild dementia
   - **2** = Moderate dementia
   - **3** = Severe dementia
   - **Why important**: This is our main classification label!

8. **Group** or **Diagnosis**
   - **Values**: "Demented" or "Nondemented"
   - **Why important**: This is what we want to predict!
   - **Demented** = Has Alzheimer's/dementia
   - **Nondemented** = Healthy control

9. **Delay** (if present)
   - Time between cognitive test and scan
   - **Why important**: For timing analysis

### 🎓 Learning Checkpoint

**Try to answer**:
1. How many total subjects are in the Excel file?
2. How many have "Demented" vs "Nondemented"?
3. What's the age range?
4. What MMSE scores do you see? (Are they mostly high or low?)

**Hint**: Use Excel's filter/sort functions to explore!

---

## 📄 Step 1C: Check the Documentation

### Action: Open the PDF File

**File location**:
```
data/oasis_cross-sectional_facts.pdf
```

**What it contains**:
- Overview of the dataset
- How data was collected
- What scanners were used
- Demographics summary
- Important notes about the data

**Why read it**: Understanding how data was collected helps you interpret results correctly!

---

## 🎯 Step 1D: Make Connections

### The Big Picture

Now that you've explored, understand this:

1. **Each subject folder** = One person's brain scan
2. **The Excel file** = Information about all subjects
3. **The connection**: Subject ID links the folder to the Excel row

**Example**:
- Folder: `OAS1_0001_MR1`
- Excel row: Find ID = "OAS1_0001"
- That row tells you: Age, Gender, Diagnosis, etc.

### What We'll Do Next

In future steps:
- Load the brain scan (`.hdr` + `.img` files)
- Get the diagnosis from Excel
- Use the scan to predict the diagnosis

---

## ✅ Step 1 Summary Checklist

After completing Step 1, you should be able to:

- [ ] Navigate to subject folders
- [ ] Identify `.hdr` and `.img` files (the brain scans)
- [ ] Open and view a `.gif` brain image
- [ ] Open the Excel metadata file
- [ ] Understand what CDR and MMSE scores mean
- [ ] Identify which subjects are "Demented" vs "Nondemented"
- [ ] Understand the connection between folders and Excel rows

---

## 🚀 Ready for Step 2?

Once you've completed Step 1 and understand:
- What files you have
- What information is available
- How it's organized

**Tell me what you found, and we'll move to Step 2!**

**Step 2 Preview**: We'll write Python code to:
- Load one brain scan
- Visualize it
- See the 3D brain structure

---

## 💡 Tips for Learning

1. **Take notes**: Write down what you discover
2. **Ask questions**: If something doesn't make sense, ask!
3. **Explore**: Don't just follow instructions - look around!
4. **Make connections**: Try to link what you see in folders to Excel rows

---

## ❓ Common Questions

**Q: Why do we need both .hdr and .img files?**
A: The `.hdr` tells software HOW to read the data, the `.img` IS the data. Both are needed!

**Q: What's the difference between CDR and Group?**
A: CDR is a detailed rating (0, 0.5, 1, 2, 3), Group is simplified (Demented/Nondemented). Both tell us about dementia status.

**Q: Why are there more subjects in Excel than folders?**
A: The Excel file contains information for all 416 subjects in the complete OASIS-1 dataset. You currently have disc1 and disc12 extracted, which gives you a subset of subjects. The Excel file is shared across all discs and contains metadata for the entire dataset, even if you haven't downloaded all 12 discs yet.

---

**Take your time with this step - understanding the data structure is crucial!**

