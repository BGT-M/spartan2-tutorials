# spartan2 Tutorials

Live tutorials for [spartan2](https://github.com/BGT-M/spartan2) — a toolkit of data mining algorithms on big graphs and time series.

## Setup

Install spartan2 before running any notebook:

```bash
pip install spartan2
```

```python
import spartan as st
```

> **Python ≥ 3.7** is required. We recommend creating a dedicated conda environment:
> ```bash
> conda create -n spartan python=3.7 && conda activate spartan
> ```

---

## Part 1: Basics

| Notebook | Description |
|----------|-------------|
| [quick_start](quick_start.ipynb) | Load tensors from files (edge lists, rich tuples, time series), build graphs and Timeseries objects |
| [tensor_usage](tensor_usage.ipynb) | DTensor and STensor operations: indexing, slicing, reduction, binary ops on CPU and GPU |
| [graph_start](graph_start.ipynb) | Build a graph from a multi-attribute edge list, compute degree distributions |

---

## Part 2: Big Graphs

### Anomaly Detection

| Notebook | Task | Description |
|----------|------|-------------|
| [HoloScope](Holoscope.ipynb) | Fraud Detection | Topology-and-spike aware fraud detection using contrast suspiciousness. [[pdf]](https://shenghua-liu.github.io/papers/cikm2017-holoscope.pdf) |
| [Fraudar](Fraudar.ipynb) | Fraud Detection | Dense subgraph detection robust to camouflage. [[pdf]](https://www.kdd.org/kdd2016/papers/files/rfp0110-hooiA.pdf) |
| [SpecGreedy](SpecGreedy.ipynb) | Fraud Detection | Unified dense subgraph detection guided by spectral analysis. [[pdf]](https://shenghua-liu.github.io/papers/pkdd2020_specgreedy.pdf) |
| [EigenSpokes](EigenSpokes.ipynb) | Anomaly Detection | Detect surprising spoke patterns in large graphs via truncated SVD. [[pdf]](https://www.cs.cmu.edu/~christos/PUBLICATIONS/pakdd10-eigenspokes.pdf) |
| [EagleMine](EagleMine.ipynb) | Anomaly Detection | Vision-guided micro-cluster detection in node-feature histograms. [[pdf]](https://shenghua-liu.github.io/papers/FGCS2021-eaglemine.pdf) |
| [EigenPulse](EigenPulse.ipynb) | Streaming Detection | Detect density surges in large streaming graphs using row-augmented SVD. [[pdf]](https://link.springer.com/chapter/10.1007/978-3-030-16145-3_39) |
| [FlowScope](FlowScope.ipynb) | Money Laundering | Detect complete money-flow paths across multi-partite transaction graphs. [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/view/5906) |
| [CubeFlow](CubeFlow.ipynb) | Money Laundering | Coupled-tensor approach for detecting money laundering in 3-partite graphs. [[pdf]](https://arxiv.org/pdf/2103.12411.pdf) |
| [MonLAD](MonLAD.ipynb) | Money Laundering | Statistical detection of money laundering agent accounts in transaction streams. [[pdf]](https://shenghua-liu.github.io/papers/wsdm2022-monlad.pdf) |
| [IAT Demo](iat_demo.ipynb) | Suspicious Behavior | Inter-arrival time analysis to detect synchronized fraudulent users. |

### Summarization

| Notebook | Task | Description |
|----------|------|-------------|
| [DPGS](DPGS.ipynb) | Graph Summarization | Degree-preserving graph summarization via MDL and greedy merging. [[pdf]](https://shenghua-liu.github.io/papers/sdm2021-dpgs.pdf) |
| [kGrass](kGrass.ipynb) | Graph Summarization | Graph structure summarization preserving edge density. [[pdf]](http://cs-people.bu.edu/evimaria/papers/Social-net.pdf) |

---

## Part 3: Time Series

| Notebook | Task | Description |
|----------|------|-------------|
| [timeseries_start](timeseries_start.ipynb) | Getting Started | Load and visualize time series data |
| [Log2Timeseries](Log2Timeseries.ipynb) | Data Processing | Convert log files to time series format |
| [BeatLex](Beatlex.ipynb) | Summarization & Forecast | Learn beat-pattern vocabulary to summarize and forecast time series. [[pdf]](https://shenghua-liu.github.io/papers/pkdd2017-beatlex.pdf) |
| [BeatGAN](BeatGAN.ipynb) | Anomaly Detection | Detect anomalous rhythms using adversarially generated time series. Requires `torch` and `tqdm`. [[pdf]](https://www.ijcai.org/Proceedings/2019/0616.pdf) |

---

## Input Data

All example datasets are in `inputData/`:

| File | Used By |
|------|---------|
| `yelp.edgelist.gz` | quick_start |
| `yelp.tensor.gz` | quick_start, graph_start, HoloScope |
| `plain_graph_small.zip` | Fraudar, SpecGreedy, EigenSpokes |
| `soc-Epinions1.tensor.gz` | kGrass, DPGS |
| `fs_in_data.csv.gz`, `fs_out_data.csv.gz` | FlowScope |
| `CFD-3/`, `CFD-4/` | CubeFlow |
| `eaglemine_data.zip` | EagleMine |
| `test_beer.tensor.gz` | EigenPulse |
| `ecg_timeseries_small.zip` | BeatLex, BeatGAN |
| `wbcovid19_test.gz` | IAT Demo |
| `cfd.csv` | MonLAD |

---

## Notes

- **BeatGAN** requires `torch` and `tqdm`. Install with `pip install torch tqdm`. R-peak detection uses a scipy-based Pan-Tompkins implementation (no biosppy needed).
- Results and intermediate files are written to `output/` (created automatically when needed).
- Model output files (`*.rows`, `*.cols`) are excluded from git via `.gitignore`.
