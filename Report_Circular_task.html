<h1 align="center">Circular Task Analysis Project</h1>

*28 of November, 2025, 11:00 AM*
*By Yann Devaux, Hugo Duchemin, Malo Bertrand-Goarin*

**Tools:**
* CSV Files (`001MoDe_R1.csv` and `001MoDe_R1.marker.csv`)
* Application: MouseReMoCo
* AI Assistants: ChatGPT, Copilot, Gemini

---

# 1. Project Definition

The project was defined following the SMART goal framework, task distribution, and a detailed work plan.

The global objective is to conduct a complete analysis of the circular task recorded by MouseReMoCo, aiming to reproduce the results and deliver them in a public GitHub repository.

### SMART Objectives

* **Specific:** Reproduce the charts and recalculate the statistics for the Circular Target Task using the provided raw data files (`001MoDe_R1...`) and a team-generated file (`main`).
* **Measurable:** Results are verified by:
    1.  Correspondence between generated charts and expected results.
    2.  Consistency of recalculated statistical values (Rec001 to Rec005) with those in the `.marker.csv` file.
    3.  Successful execution on an auto-generated file.
    4.  Presence of a 1-2 page report and a clean repository structure.
* **Attainable:** The allocated time and role distribution (Manager, Code, Report) make the objective easily achievable, provided deadlines are respected and team communication remains effective.
* **Realistic:** The team possesses the necessary skills and tools (Python, GitHub, MouseReMoCo) for movement data analysis and online collaboration.
* **Time-bound:** The project is framed by established meeting dates: 11/13 (Organization), 11/19 (Comprehension/Tasks), 11/28 (Review/Merge), with delivery expected shortly after the final review.

---

# 2. Detailed Work Plan by Role

### **Hugo (Manager & "Circles" Code)**

**Managerial Responsibilities (Project Management):**
* Create the GitHub repository based on the `Python-for-HMS-Template`.
* Ensure access and collaboration rights for Yann and Malo.
* Supervise contribution integration; remain the sole person authorized to merge Pull Requests (PRs).
* Manage merge conflicts if necessary.
* Ensure deadlines and objectives are met.

**Coding Responsibilities (Circular Analysis):**
* Develop the core code to read and analyze circular task data.
* Verify center coordinates ($C_x, C_y$) and target radius ($R_{task}$) from header data.
* Identify metrics specific to "circles": effective radius ($R_e$), effective tolerance ($T_e$), error percentage, and number of laps (`nLaps`).
* Read raw data with automated range selection per record.
* Create a loop for processing each record.
* Display each graph.

### **Yann ("Waves" Code / Performance Analysis)**

**Coding Responsibilities (Speed and Throughput Analysis):**
* Develop code to calculate performance metrics and information throughput (related to movement "waves").
* Identify movement time per lap ($MT/lap$).
* Separate the values acquired by MouseReMoCo into 5 different records.
* For each record, generate 1 graph composed of 3 curves: X position/time, Y position/time, and target status (inside/outside) over time.
* Display all 5 records on a single superimposed graph.
* Display headline information from both CSV files.

### **Malo (Outreach, Report, and Documentation)**

**Documentation and Reporting Responsibilities:**
* Write the Analysis Report (1-2 pages).
* Explain the most interesting difficulties encountered (particularly the `numpy`/`matplotlib` constraint) and the solutions implemented.
* Detail the calculations for transitioning from `001MoDe_R1.csv` to `001MoDe_R1.marker.csv`.
* Explain task distribution and team organization (this plan).
* Write the general repository report (`README`).
* Perform the MouseReMoCo task to verify code reproducibility and correct execution.

### **Common Tasks**

* **MouseReMoCo Exploration:** Each member must experiment with the software to understand how data is recorded (cursor/target position, time, events).
* **Data Reading & Cleaning:** Develop a function to read `.csv` and `.marker.csv` files **without using pandas** (requires line-by-line reading with `numpy` or `os`/`numpy.loadtxt` functions, handling headers carefully).
* **Integration:** Integrate the complete code into a `.ipynb` file.
* **Data Generation:** Each team member tests generating a clean data file for the final test.
* **Cross-Verification:** Conduct a code and result review of teammates' work before merging.

---

### Timeline

| Date | Objective | Lead Responsible | Deliverables/Results |
| :--- | :--- | :--- | :--- |
| **13/11** | Work organization, GitHub repository creation. | Hugo (Manager) | Repository created, Roles assigned, SMART plan defined. |
| **19/11** | Deep understanding of the task (MouseReMoCo) and coding task assignment. | All (Malo for concepts) | First data reading functions, work branches created. |
| **28/11** | Task review, result verification, final Merge. | Hugo (Manager) | Calculations and graphs verified, Report and README finalized. |

---

# 3. Limitations and Common Difficulties

### *Technical Constraint: Numpy and Matplotlib Only*

**Difficulty 1: Reading Non-Standard CSV Files**
The `.csv` file contains a non-standard header (metadata). Using `pandas` would have made this trivial.

* **Solution:** We must read the header (lines starting with specific characters or simply the first N lines) to extract parameters (e.g., $R_{e}, R_{task}, ID$) before loading the raw numerical data (time, x, y) into a numpy array using the `skip_header` argument.

**Difficulty 2: Advanced Graphical Representation**
`matplotlib` is powerful but requires more code for specific charts (X-Y trajectories, velocity vs. angle) compared to statistical-oriented tools.

* **Solution:** Clearly structure plotting functions and utilize subplot features (`plt.subplots()`) to organize visuals efficiently.

### *Conceptual Difficulty: Data Interpretation*

**Difficulty 3: Precise Lap Detection**
The system counts laps (`nLaps`). The code must reproduce MouseReMoCo's internal logic to determine when a lap is successful or completed, typically based on crossing a 360-degree angle or a specific axis.

* **Solution:** Examine the CircularTarget task documentation to find the exact definition of a "lap".

**Difficulty 4: Marker Synchronization**
Timestamps in markers (`.marker.csv`) and raw data (`.csv`) must be synchronized to isolate each recording (Rec001 to Rec005). Times are in Unix milliseconds.

* **Solution:** Calculate the time elapsed since the first `DoRecord` event to align data samples with the 20.000-second intervals defined by the markers.

**Difficulty 5: Respect the scales of the figure without modyfing itself**

* **Solution:** Using the : *ax.set_label* to change the scale without crush it
