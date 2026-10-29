# ML-Aided Optimisation of MOSFET Device Parameters

BTech project, NIT Calicut (Jan – May 2026) · Team of 4 · Guide: Dr. Jaikumar M G

**My role:** Silvaco TCAD recalibration and generation of the simulation dataset.

📄 **[Read the full report (PDF)](report.pdf)**

## Problem

A single Silvaco process–device run takes minutes. Exploring how process parameters set the threshold voltage (Vth) needs hundreds of runs. This project replaces the TCAD loop with an ML surrogate that predicts Vth in milliseconds.

## Method

1. **TCAD flow:** recalibrated a Silvaco Athena (process) + Atlas (device) nMOSFET flow.
2. **Sampling:** 700 simulations across gate oxide time, channel implant dose and gate length, using Latin Hypercube Sampling.
3. **Extraction:** Vth from Id–Vg curves by the maximum-transconductance method.
4. **Cleaning:** removed non-converged runs → 686-sample dataset.
5. **Models:** trained and compared regression surrogates; deployed the best as a web app.

## Results

| Model | R² (test) |
|---|---|
| XGBoost | **0.967** |

## Tools

Silvaco Athena, Atlas, TonyPlot · Python (pandas, scikit-learn, XGBoost)
