# Mouse Trajectory Data Analysis

This project loads, processes, and visualizes mouse trajectory data from a CSV file.  
It automatically detects the differents recorsd (time segments), recenters X and Y coordonates, 
and generates several plots (individual and combined views) to show the position of X and Y over the time,
and if the mouse in on the target or not.

---
## 📂 Project Contents

- `Position_Over_Time_Graph.ipynb` — main script containing data loading, round detection, and plotting functions.
- `001MoDe_R1.csv` — example dataset used by the script.
- `001MoDe_R1.marker.csv` — example dataset used by the script.
- `README.md` — documentation for the project.
---

## 🚀 Features

- Automatic CSV loading (semicolon-separated).
- Extraction of the required columns:
  - `timestamp`
  - `mouseX`
  - `mouseY`
  - `mouseInTarget`
- Coordinate centering around a fixed reference point.
- Automatic round detection (`timestamp != 0`).
- Visualization tools:
  - Individual plots for each round (X, Y, target)
  - Combined plot displaying all rounds with time offsets
- Clean, modular, and easy-to-read code structure.

---

## 📊 Example Outputs

- X and Y trajectories per round  
- Target-entry visualization  
- Combined time-series view with boundaries  

---

## 🔧 Usage

1/ Copy paste the code, or the repo
2/ Make sure your data file is well formated (use MouseReMoCo software : https://github.com/DenisMot/mouseReMoCo; and seperate columns in your xls file !) 
3/ Play with the software !




