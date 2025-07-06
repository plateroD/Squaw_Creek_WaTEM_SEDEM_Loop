# Squaw_Creek_WaTEM_SEDEM_Loop
Automated batch runner for WaTEM/SEDEM: loops annual simulations (2009–2020) with configurable climate‐forcing integration.

# WaTEM/SEDEM Batch Runner

A simple Python wrapper to automate annual runs of the WaTEM/SEDEM soil‐erosion model.  
This script takes your base `.ini` configuration and, for each year in a user-specified range,  
1. updates the start date,  
2. generates a year-specific output folder,  
3. optionally swaps in year-specific RUSLE R factors (e.g. from Daymet),  
4. and launches the WaTEM/SEDEM executable—no manual editing of control files required.

---

##  Features

- **Yearly Loop**: Runs simulations for any contiguous range, e.g. 2009–2020.  
- **INI Templating**: Reads your master `.ini`, replaces `date` & `output directory` entries, writes `run_<year>.ini`.  
- **Optional Climate Forcing**: Hook in a routine to pull annual precipitation (Daymet, Mesonet, etc.) and compute RUSLE R per year.  
- **Error Handling & Logging**: Stops if the model returns an error code, with clear console messages.  

---

## ⚙Prerequisites

- **Python 3.6+**  
- WaTEM/SEDEM executable (Windows `.exe` or Linux binary)  
- (Optional) [`pydaymet`](https://github.com/haowen-xu/pydaymet) or your preferred climate API for variable R factors  

---

##  Installation

1. Clone this repo:  
   ```bash
   git clone https://github.com/<your-username>/watem-sedem-batch-runner.git
   cd watem-sedem-batch-runner

watem-sedem-batch-runner/
├─ batch_runner.py
├─ README.md
└─ Squaw_Creek/
   ├─ Input/
   │  └─ Squaw_Creek.ini
   └─ Output/
      ├─ 2009/
      ├─ 2010/
      └─ …


