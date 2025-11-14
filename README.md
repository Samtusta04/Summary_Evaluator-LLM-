# AI-Based Automated Grading System for Lecture Summaries

This project implements a fully automated, explainable, and reproducible AI grading system that evaluates student-written summaries by comparing them to lecture transcripts.

## Features

- **Automated Processing**: Processes all student summaries from an Excel file automatically
- **Hybrid Evaluation**: Uses embedding-based similarity (Sentence Transformers) combined with rule-based scoring
- **Explainable Scoring**: Provides detailed 2-3 sentence explanations for each score
- **Multiple Criteria**: Evaluates based on:
  - Coverage of main lecture points (30%)
  - Semantic similarity to lecture content (25%)
  - Clarity and coherence (20%)
  - Completeness (15%)
  - Grammar and conciseness (10%)

## Requirements

- Python 3.8 or higher
- Required packages listed in `requirements.txt`

## Installation

1. Install the required packages:
```bash
pip install -r requirements.txt
```

## Usage

### Step 1: Prepare Input Files

Place the following files in the project directory:
- `lecturetranscript.docx` - The full lecture transcript in DOCX format
- `studentsummaries.xlsx` - Excel file with columns:
  - Email Address
  - Name of the Student
  - Roll Number
  - Institute
  - Summary

### Step 2: Configure Roll Number and Rename Files

1. **Rename the notebook file** to `SummaryEvaluation<YourRollNumber>.ipynb` (e.g., `SummaryEvaluation12345.ipynb`)

2. Open the notebook and set your roll number in the first code cell:
```python
ROLL_NUMBER = "YOUR_ROLL_NUMBER"  # Replace with your actual roll number (e.g., "12345")
```

**Note**: The output file will be automatically named `Gradedresults<YourRollNumber>.xlsx` based on this variable.

### Step 3: Run the Notebook

1. Open `SummaryEvaluation.ipynb` in Jupyter Notebook or VS Code
2. Run all cells sequentially (Cell → Run All)
3. The system will:
   - Load the lecture transcript
   - Load student summaries
   - Evaluate each summary
   - Generate scores and explanations
   - Export results to `Gradedresults<YourRollNumber>.xlsx`

## Output

The system generates an Excel file `Gradedresults<YourRollNumber>.xlsx` with the following columns:
- Email Address
- Name
- Roll Number
- Institute
- Original Summary
- Numerical Score (0-10)
- Short explanation (2-3 sentences)

## How It Works

1. **Text Extraction**: Extracts text from the DOCX lecture transcript
2. **Key Point Extraction**: Identifies key sentences/points from the transcript
3. **Semantic Analysis**: Uses Sentence Transformers to compute semantic similarity
4. **Multi-Criteria Evaluation**: Scores each summary across 5 dimensions
5. **Explanation Generation**: Creates detailed justifications referencing specific strengths and weaknesses
6. **Excel Export**: Automatically generates the output file with all required columns

## Model Information

The system uses the `all-MiniLM-L6-v2` Sentence Transformer model, which is:
- Lightweight and fast
- Pre-trained on large text corpora
- Effective for semantic similarity tasks
- Downloads automatically on first use

## Notes

- The first run may take longer as the Sentence Transformer model downloads (~80MB)
- Processing time depends on the number of students and summary lengths
- All evaluation logic is contained within the notebook for full reproducibility

## Troubleshooting

**Error: "Could not find summary column"**
- Ensure your Excel file has a column named "Summary" (case-insensitive)

**Error: "File not found"**
- Verify that `lecturetranscript.docx` and `studentsummaries.xlsx` are in the same directory as the notebook

**Model download issues**
- Ensure you have an active internet connection for the first run
- The model will be cached for subsequent runs

