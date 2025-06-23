# 🎓 GPA Badge Generator
**for your special repository README.md!**

<img src="gpa_badge.svg" alt="GPA badge">

GPA Badge Generator is a tool that reads an Excel file (`grades.xlsx`), calculates your GPA, and automatically generates a visual SVG badge to display it and update your profile README.md!

---

## 📦 Features

- 🎯 **Automatic GPA Calculation**  
  Calculates your GPA based on course data stored in `assets/grades.xlsx`.

- 🖼️ **SVG GPA Badge Generation**  
  Creates a clean, circular visual badge showing your GPA directly in your repository.

- 🤖 **GitHub Actions Automation**  
  - Runs every Monday at midnight (UTC)
  - Can be manually triggered (`workflow_dispatch`)
  - Automatically runs when `assets/grades.xlsx` is modified

- 📌 **Auto-updates README**  
  Replaces or inserts the latest GPA badge into your `README.md` automatically.

---

## 📁 Project Structure

```
📦 your-repo/
├── .github/workflows/
│   └── generate_gpa_badge.yml     # GitHub Actions workflow
├── assets/
│   └── grades.xlsx                # Excel file used for GPA calculation
├── generate_gpa.py                # Python script for GPA calculation and badge generation
├── gpa_badge.svg                  # Automatically generated GPA badge
├── requirements.txt               # Python dependencies
└── README.md                      # This document (auto-updated with badge)
```

---

## 📊 Excel File Format (`assets/grades.xlsx`)

| Column I (Credits) | Column K (Grade) |
|--------------------|------------------|
| 3                  | A+               |
| 3                  | B0               |
| 2                  | C+               |
| 1                  | P                |

- Grades must follow the format: `A+`, `A0`, `B+`, ..., `F`, `P`, `NP`
- `P` and `NP` grades are excluded from GPA calculation
- Data is read starting from **row 5**, upper rows can be left blank or used for headers

- This file format is based on Sejong University's academic transcript export: `세종대학교 기이수성적조회-*.xlsx`

---

## ⚙️ How to Use

1. Update `assets/grades.xlsx` with your transcript data.
2. Add secrets in this Repository settings **GH_USERNAME, GH_EMAIL, GH_PAT**.
- **GH_USERNAME** is your github id, **GH_EMAIL** is your github email, and **GH_PAT** is your github Personal Access Token(PAT).
3. Commit and push the changes to GitHub.
4. GitHub Actions will automatically calculate the GPA and update `gpa_badge.svg` and `README.md` in profile repository.
5. Check your README to see the updated GPA badge.

- Github actions push .svg file to your Profile repository in /gpa-badge-generator.

---

## 🧪 Local Testing (Optional)

```bash
pip install -r requirements.txt
python generate_gpa.py
```

---

## 🛠️ Tech Stack

- Python 3.10+
- openpyxl
- GitHub Actions
- SVG (for vector badge rendering)

---

## 📝 License

MIT License  
You are free to use and modify this project.

---

## 🙋‍♀️ Contributions

Pull Requests and Issues are always welcome!  
Feel free to contribute new badge styles, GPA scale options (e.g. 4.0 / 4.3 / 5.0), and more 😊
