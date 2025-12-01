# Circular Task — README

## **Prerequisites**
Install **Python 3.9+** and the required libraries:  
- **NumPy**  
- **MatPlotLib**

---

## **Expected files**
The script uses two files located in the same folder:

- **001MoDe_R1.csv** — cursor data (timestamp, mouseX, mouseY, mouseInTarget)  
- **001MoDe_R1.marker.csv** — events (start / pause / record)

If you are using your own data (extracted from **RemCoco**), make sure to import the correct files with the correct names:  
- 1 file for the **cursor data**  
- 1 file for the **events**

---

## **Execution (run)**

When running the script, it will automatically:

- Load the data (`np.genfromtxt`)  
- Read and print the header metadata  
- Read the markers (lines 4–26)  
- Center the coordinates around **centerX / centerY**  
- Automatically detect all the different **records**

---

## **Generate**

The script produces:

- One **circular plot** for each record  
- **X / Y / InTarget** curves over time  
- A **global trajectory** plot  
- A **time-aligned rounds** plot  

---

## **Internal script organization**

### *The code performs:*
- Extraction of useful columns: **timestamp**, **mouseX**, **mouseY**, **mouseInTarget**  
- Detection of records via **timestamp discontinuities**  
- Per-record extraction: **relative time** + **centered coordinates**

### *Plots:*
- Target (inner and outer circles)  
- Points **inside the target** (green) / **outside the target** (red)  
- Complete trajectories  
- Time-series graphs  

---

## **Common issues**

- **RuntimeWarning (NaN):** normal if the CSV contains empty or malformed lines.  
- **Empty plots:** check that the CSV contains non-zero X/Y values (except during record switches).  

---
