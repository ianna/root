\addtogroup tutorial_dataframe

@{

[RDataFrame](classROOT_1_1RDataFrame.html) offers a high-level interface for the analysis of data stored in [TTree](classTTree.html)s, [CSV files](classROOT_1_1RDF_1_1RCsvDS.html), and [other data formats](classROOT_1_1RDF_1_1RDataSource.html).

In addition, multi-threading and other low-level optimizations allow users to exploit all the resources available on their machines transparently.

In a nutshell:
~~~{.cpp}
ROOT::EnableImplicitMT(); // Enable ROOT's implicit multi-threading
ROOT::RDataFrame d("myTree", "file_*.root"); // Interface to TTree and TChain
auto histoA = d.Histo1D("Branch_A");  // Book the filling of a histogram
auto histoB = d.Histo1D("Branch_B");  // Book the filling of another histogram
// Data processing is triggered by the next line, which accesses a booked result for the first time
// All booked results are evaluated during the same parallel event loop.
histoA->Draw(); // <-- event loop runs here!
histoB->Draw(); // HistoB has already been filled, no event loop is run here
~~~

Explore the examples below or go to [RDataFrame's user guide](classROOT_1_1RDataFrame.html).

---

# Examples

<div class="tabs">

### C++ Tutorials

- **Basic Examples:**
  - [df000_simple.C](df000_simple.C)
  - [df001_introduction.C](df001_introduction.C)
  - [df002_dataModel.C](df002_dataModel.C)
  - [df003_profiles.C](df003_profiles.C)
  - [df004_cutFlowReport.C](df004_cutFlowReport.C)
  - [df005_fillAnyObject.C](df005_fillAnyObject.C)
  - [df006_ranges.C](df006_ranges.C)
  - [df007_snapshot.C](df007_snapshot.C)
  - [df008_createDataSetFromScratch.C](df008_createDataSetFromScratch.C)
  - [df009_FromScratchVSTTree.C](df009_FromScratchVSTTree.C)

- **Advanced Examples:**
  - [df010_trivialDataSource.C](df010_trivialDataSource.C)
  - [df012_DefinesAndFiltersAsStrings.C](df012_DefinesAndFiltersAsStrings.C)
  - [df013_InspectAnalysis.C](df013_InspectAnalysis.C)
  - [df014_CSVDataSource.C](df014_CSVDataSource.C)
  - [df015_LazyDataSource.C](df015_LazyDataSource.C)
  - [df016_vecOps.C](df016_vecOps.C)
  - [df017_vecOpsHEP.C](df017_vecOpsHEP.C)

---

### Python Tutorials

- **Basic Examples:**
  - [df000_simple.py](df000_simple.py)
  - [df001_introduction.py](df001_introduction.py)
  - [df002_dataModel.py](df002_dataModel.py)
  - [df003_profiles.py](df003_profiles.py)
  - [df004_cutFlowReport.py](df004_cutFlowReport.py)
  - [df006_ranges.py](df006_ranges.py)
  - [df007_snapshot.py](df007_snapshot.py)

- **Advanced Examples:**
  - [df008_createDataSetFromScratch.py](df008_createDataSetFromScratch.py)
  - [df010_trivialDataSource.py](df010_trivialDataSource.py)
  - [df012_DefinesAndFiltersAsStrings.py](df012_DefinesAndFiltersAsStrings.py)
  - [df014_CSVDataSource.py](df014_CSVDataSource.py)
  - [df016_vecOps.py](df016_vecOps.py)
  - [df017_vecOpsHEP.py](df017_vecOpsHEP.py)

</div>

@}
