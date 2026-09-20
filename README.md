# Bypassing Tomographic Reconstruction: 3D Aneurysm Hemodynamics from 2D Projections using PINNs

> **Project Report & Experimental Repository**  
> Physics-Informed Neural Networks (PINNs) + Hidden Fluid Mechanics (HFM) + Forward Radon Projection for reconstructing hidden 3D aneurysm hemodynamics from limited 2D observations.

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-supported-EE4C2C.svg)](https://pytorch.org/)
[![PINNs](https://img.shields.io/badge/Physics--Informed%20ML-PINNs-orange.svg)](#technical-approach)
[![W%26B](https://img.shields.io/badge/Tracking-Weights%20%26%20Biases-yellow.svg)](https://wandb.ai/)
[![Status](https://img.shields.io/badge/status-Phase%201%20completed-success.svg)](#project-status)

## Project Report

**Title:** *Bypassing Tomographic Reconstruction: Inferring 3D Aneurysm Hemodynamics from 2D Projections using Physics-Informed Neural Networks*

**Student:** Abhigyan Srivastav  
**Program:** B.Tech. Electronics & Communication Engineering  
**Institution:** Faculty of Technology, University of Delhi  
**Faculty Guide:** Dr. Sangeeta Yadav, Computer Science & Engineering  
**Project Period:** 02 February 2026 – 21 April 2026

The project investigates whether hidden 3D blood-flow behaviour inside a cerebral aneurysm can be inferred without first performing conventional tomographic reconstruction. The accompanying report documents the mathematical formulation, implementation, ablation studies, projection experiments, results, limitations, and future work. :contentReference[oaicite:3]{index=3}

### 📄 Full Project Report

**[Open / View the Complete Project Report (PDF)](https://abhigyanshrivastav.github.io/PINNs_Aneurysm_Tracking/Final_Project_Report_PINN.pdf)**

This repository serves as the technical companion and GitHub Pages entry point for the project report.

---

## Abstract

Conventional computational hemodynamics generally requires a resolved 3D geometry before fluid-flow simulation can be performed. Medical imaging systems, however, often provide 2D projections or line-integral measurements, creating a reconstruction bottleneck.

This project investigates a **Physics-Informed Neural Network (PINN)** framework for inferring continuous 3D velocity and pressure fields from sparse observations while reducing reliance on conventional tomographic reconstruction.

The system combines:

- an **8-layer neural network** acting as a continuous fluid solver,
- **Navier–Stokes PDE constraints** embedded in the training objective,
- a custom **Forward Radon Transform / ray-casting module** integrated into the PyTorch pipeline, and
- systematic experiments covering model capacity, data sparsity, physical constraints, noise robustness, and projection ambiguity.

The documented experiments include an 80% sparse-data ablation, zero-physics control, 10% Gaussian-noise stress testing, adaptive physics-loss weighting, and single-axis projection analysis. A multi-angle orthogonal projection extension is implemented as ongoing work but remains constrained by GPU memory requirements.

---

## Research Motivation

The project studies the gap between:

```text
2D Clinical Measurements
        ↓
Tomographic Reconstruction
        ↓
3D Geometry
        ↓
CFD / Hemodynamic Analysis
