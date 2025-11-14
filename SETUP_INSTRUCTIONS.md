# Quick Setup Instructions

## File Naming Requirements

Before running the system, ensure your files are named correctly:

1. **Notebook/Script**: Rename to `SummaryEvaluation<YourRollNumber>.ipynb` or `.py`
   - Example: If your roll number is `12345`, name it `SummaryEvaluation12345.ipynb`

2. **Input Files** (place in the same directory):
   - `lecturetranscript.docx` - Lecture transcript
   - `studentsummaries.xlsx` - Student summaries

3. **Output File** (auto-generated):
   - `Gradedresults<YourRollNumber>.xlsx` - Graded results

## Step-by-Step Setup

1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Rename the notebook**:
   - Rename `SummaryEvaluation.ipynb` to `SummaryEvaluation<YourRollNumber>.ipynb`

3. **Update roll number**:
   - Open the notebook
   - In the first code cell, change:
     ```python
     ROLL_NUMBER = "YOUR_ROLL_NUMBER"  # Change this!
     ```
   - To:
     ```python
     ROLL_NUMBER = "12345"  # Your actual roll number
     ```

4. **Place input files** in the same directory:
   - `lecturetranscript.docx`
   - `studentsummaries.xlsx`

5. **Run the notebook**:
   - Open in Jupyter Notebook or VS Code
   - Run all cells (Cell → Run All)

6. **Check output**:
   - The file `Gradedresults<YourRollNumber>.xlsx` will be created automatically

## Deliverables Checklist

After running, ensure you have:

- [ ] `SummaryEvaluation<YourRollNumber>.ipynb` - Code implementation
- [ ] `Gradedresults<YourRollNumber>.xlsx` - Auto-generated output
- [ ] `Implementation<YourRollNumber>.mp4` - Screen recording (you need to create this)

## Screen Recording Tips

For the `Implementation<YourRollNumber>.mp4` video (max 5 min):

1. Show loading the input files
2. Show running the evaluation process
3. Show the generated output Excel file
4. Briefly explain the evaluation criteria

You can use:
- Windows: Built-in Screen Recorder (Win+G) or OBS Studio
- Mac: QuickTime Player or ScreenFlow
- Linux: OBS Studio or SimpleScreenRecorder

