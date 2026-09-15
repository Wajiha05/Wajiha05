<!--
  GitHub Profile README
  Replace every Wajiha05 with your GitHub handle.
-->

<div align="center">

# `Wajiha Manaf Sahi`

### RTL Design & Digital IC Design & Verification Engineer
**Building the silicon that runs the models — and the models that justify the silicon.**

<sub>Verilog · FPGA/ASIC Flows · AI/ML Hardware Accelerators · RISC-V · Static Timing Analysis · Cadence EDA</sub>

<br/>

`ARCHITECTURE` ─── `RTL` ─── `VERIFICATION` ─── `SYNTHESIS` ─── `SILICON`

</div>

---

## ▍Core Specializations

I work at the seam where a neural network stops being math and starts being wires, registers, and timing closure. Most engineers pick a side of that boundary. I'm deliberately building on both.

**Hardware–software co-design** is not a buzzword in my workflow — it's the actual loop:

```
  PyTorch model  →  layer/dataflow analysis  →  microarchitecture decision
       ↑                                                    ↓
  accuracy & throughput  ←  RTL implementation  ←  Verilog datapath design
       ↑                                                    ↓
  ────────  simulation, coverage, synthesis, timing  ────────
```

- **RTL Design** — Synthesizable Verilog for arithmetic datapaths, pipelined MAC arrays, memory hierarchies, and FSM-driven control logic.
- **Functional Verification** — Directed and self-checking Verilog testbenches, waveform-level debug, and RTL simulation.
- **AI Accelerator Microarchitecture** — Systolic arrays, dataflow scheduling (weight/output stationary), quantized fixed-point arithmetic, on-chip buffer sizing.
- **Model-Aware Hardware Thinking** — Reading a model's layer shapes and deciding what the hardware should look like, rather than treating the network as a black box.

---

## ▍Technology Stack

<table>
<tr>
<td valign="top" width="33%">

### ⬡ Hardware Description & Verification
<sub>RTL languages, verification methodology</sub>

<br/>

![Verilog](https://img.shields.io/badge/Verilog-2F333A?style=for-the-badge&logo=v&logoColor=white)

<sub>*SystemVerilog & UVM — currently learning*</sub>

</td>
<td valign="top" width="33%">

### ⬢ AI Frameworks & Compute
<sub>Model development, parallel compute</sub>

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

</td>
<td valign="top" width="33%">

### ⬛ EDA & Synthesis Tools
<sub>Implementation, timing, signoff</sub>

<br/>

![Vivado](https://img.shields.io/badge/Xilinx_Vivado-E31937?style=for-the-badge&logo=xilinx&logoColor=white)
![Cadence Virtuoso](https://img.shields.io/badge/Cadence_Virtuoso-6E2C00?style=for-the-badge&logoColor=white)
![Cadence Genus](https://img.shields.io/badge/Cadence_Genus-6E2C00?style=for-the-badge&logoColor=white)
![Cadence Innovus](https://img.shields.io/badge/Cadence_Innovus-6E2C00?style=for-the-badge&logoColor=white)

</td>
</tr>
</table>

<div align="center">

| Category | Stack |
|:---|:---|
| **RTL & Verification** | ![Verilog](https://img.shields.io/badge/Verilog-2F333A?style=flat-square&logoColor=white) · SystemVerilog (learning) · RTL testbenches |
| **AI / Compute** | Python · PyTorch · C/C++ · FPGA-based AI/ML accelerators · fixed-point arithmetic |
| **EDA Toolchain** | Cadence Virtuoso · Genus · Innovus · Vivado |

</div>

---

## ▍Flow Deep-Dive

<table>
<tr>
<td valign="top" width="50%">

### Silicon — RTL & Verification

**Design Languages**
- Verilog (primary)
- SystemVerilog *(currently learning)*

**Verification**
- Self-checking testbenches
- Waveform-level debug
- SystemVerilog & UVM *(currently learning)*

**Implementation Flow**
- RTL → Synthesis → Timing → Bitstream
- Static timing analysis (STA)
- Timing constraints (SDC/XDC) and STA
- FPGA implementation and prototyping of RTL

</td>
<td valign="top" width="50%">

### Intelligence — ML & Compute

**Frameworks**
- PyTorch

**AI Hardware**
- FPGA-based AI/ML acceleration
- Fixed-point arithmetic
- Hardware accelerator architecture

**Model → Hardware**
- Quantized/fixed-point computation
- Dataflow and microarchitecture considerations
- Throughput / latency / area trade-offs

**Tooling**
- Python, NumPy

</td>
</tr>
</table>

---

## ▍Featured Work

Three accelerators, three different compute patterns — a systolic array (dense linear algebra), a softmax unit (nonlinear, numerically sensitive), and a KNN engine (search/comparison, not arithmetic-bound). Together they cover most of what actually sits on the datapath of a real inference chip.

<table>
<tr><td width="100%">

### ⬡ Systolic Array — GEMM Accelerator
**`Verilog` · `Vivado` · `Systolic Array Architecture`**

A tiled **systolic-array architecture** for accelerating GEMM, using processing elements, tile control, and a global memory interface.

| | |
|:---|:---|
| **Microarchitecture** | Weight-stationary systolic-array approach with 3×3 processing-element tiles |
| **Arithmetic** | Fixed-point matrix multiplication datapath |
| **Verification** | RTL simulation and output comparison against expected results |
| **Implementation** | 9×9 GEMM explored using 3×3 tiled processing elements |

> **Why it matters:** the hardware datapath produces the expected matrix-multiplication results. RTL correctness and hardware-efficient architecture are the core goals of the project.

**→ [`GEMM / Systolic Array repository`](https://github.com/Wajiha05)**

</td></tr>
</table>

<table>
<tr><td width="100%">

### ⬢ Hardware Softmax — Nonlinear Activation Accelerator
**`Verilog` · `Vivado` · `Fixed-Point Arithmetic`**

A hardware Softmax core using a two-pass architecture with max-subtraction, fixed-point arithmetic, and LUT-based exponential/reciprocal approximations.

| | |
|:---|:---|
| **Approximation** | LUT-based exponential and reciprocal with max-subtraction for numerical stability |
| **Precision** | Q8.8 fixed-point |
| **Verification** | RTL output verification against expected Softmax results |
| **Interface** | AXI4-Lite-style control/interface design |

> **Why it matters:** attention layers call softmax constantly. An accelerator that nails GEMM but stalls on softmax just moves the bottleneck — this closes that gap.

**→ [`Softmax Accelerator repository`](https://github.com/Wajiha05)**

</td></tr>
</table>

<table>
<tr><td width="100%">

### ⬡ KNN Accelerator — Distance & Search Engine
**`Verilog` · `Vivado`**

A Verilog K-Nearest-Neighbors accelerator for classification, using squared Euclidean distance, top-K neighbour selection, and FSM-based control.

| | |
|:---|:---|
| **Distance metric** | Squared Euclidean distance |
| **Top-K selection** | Top-K neighbour update/selection logic |
| **Verification** | RTL simulation and classification-result checking |
| **Results** | K = 7 · 64-entry reference set · 16-bit fixed-point · 36,911 LUTs · 2,087 FF · 1454.493 ns |

> **Why it matters:** most "AI accelerator" portfolios are all matrix multiply. KNN forces a different microarchitecture — it's proof the co-design thinking generalizes beyond GEMM.

**→ [`KNN Accelerator repository`](https://github.com/Wajiha05)**

</td></tr>
</table>

<table>
<tr>
<td width="50%" valign="top">

### ⬡ RISC-V Processor & Cache
`Verilog` · `Computer Architecture`

Worked with pipelined RISC-V processor architecture and cache design as part of digital hardware/architecture projects.

**→ [`RISC-V / processor repositories`](https://github.com/Wajiha05)**

</td>
<td width="50%" valign="top">

### ⬢ ASIC/FPGA Flow Studies
`Cadence`

Hands-on study of RTL-to-synthesis and ASIC/FPGA implementation flows, including synthesis and Static Timing Analysis.

**→ [`Wajiha05 GitHub`](https://github.com/Wajiha05)**

</td>
</tr>
</table>

---

## ▍Activity

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Wajiha05&show_icons=true&hide_border=true&theme=dark&title_color=76B900&icon_color=76B900&text_color=C9D1D9&bg_color=0D1117&include_all_commits=true&hide=issues,contribs" alt="GitHub Stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Wajiha05&layout=compact&hide_border=true&theme=dark&title_color=76B900&text_color=C9D1D9&bg_color=0D1117&langs_count=8" alt="Top Languages" />

<br/><br/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Wajiha05&hide_border=true&background=0D1117&stroke=30363D&ring=76B900&fire=76B900&currStreakLabel=C9D1D9&sideLabels=C9D1D9&dates=8B949E" alt="Streak" />

<br/><br/>

![Profile Views](https://komarev.com/ghpvc/?username=Wajiha05&color=76B900&style=for-the-badge&label=PROFILE+VIEWS)

</div>

---

## ▍Currently

```verilog
// roadmap.v
always @(posedge learning) begin
    systemverilog    <= learning;
    uvm              <= learning;
    accelerator      <= improving(current_design);
    reading          <= "Computer Architecture: A Quantitative Approach";
end
```

- Currently learning **SystemVerilog and UVM verification methodologies**
- Improving AI accelerator RTL and exploring **synthesis + STA flows**
- Studying how quantization choices upstream change area and timing downstream

---

<div align="center">

### ▍Contact

[**LinkedIn**](https://linkedin.com/in/wajiha-manaf-sahi-18288b319) · **Email available on request**

<sub>Open to RTL Design and Design Verification roles — especially where the workload is AI.</sub>

</div>
