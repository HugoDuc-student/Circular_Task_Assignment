Circular Task — README
**Prerequisites**
Install Python 3.9+ and the required libraries:
Numpy and MatPlotLib

**Expected files**
The script uses two files located in the same folder:
001MoDe_R1.csv — cursor data (timestamp, mouseX, mouseY, mouseInTarget)
001MoDe_R1.marker.csv — events (start/pause/record)

If you are using your proper data (extract from RemCoco), import the good files with the good names : 
1 file for the cursor data 
1 file for the events 

**Execution (run):**
The script will automatically:
Load the data (np.genfromtxt)
Read and print the header metadata
Read the markers (lines 4–26)
Center coordinates around centerX / centerY
Automatically detect the different records

**Generate:**
a circular plot for each record
X / Y / InTarget curves over time
a global trajectory plot
a time-aligned rounds plot

**Internal script organization**
*The code performs:*
Extraction of useful columns: timestamp, mouseX, mouseY, mouseInTarget
Record detection via timestamp discontinuities
Per-record extraction: relative time + centered coordinates

*Plots:*
target (inner/outer circles)
points inside target (green) / outside target (red)
complete trajectories
time-series plots

**Common issues**
RuntimeWarning (NaN): normal if the file contains empty/malformed lines.
Empty plots: check that the CSV actually contains non-zero X/Y values (except when you change records)
