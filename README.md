Multi-Axis Force/Torque Sensor ML Calibration System

This project implements a robust, two-stage Machine Learning (ML) calibration system for simulating and calibrating 6-axis Force/Torque (F/T) sensors. It is designed to model and compensate for complex non-linear effects, particularly temperature drift and material creep, achieving high-precision calibration using the PyTorch framework.

🌟 Features

    Advanced Sensor Simulation: Includes a data generator that synthesizes realistic F/T, temperature, and raw voltage data, incorporating noise, non-linear temperature effects (zero offset and sensitivity), and a logarithmic creep model.

    Two-Stage Calibration Pipeline:

        Stage 1 (LSTSQ): Fast initialization of the main Compliance (C), Zero Offset (Z), and Sensitivity (S) matrices using Least Squares.

        Stage 2 (ML Global Optimization): Refinement of all 74 model parameters using an Adam optimizer in PyTorch to globally minimize the error, accurately capturing non-linear and time-dependent effects.

    Creep Compensation: Utilizes a physical-based logarithmic creep model: Vout​∝1+Ccreep​⋅log(1+tcreep​/τcreep​).

    Optimized for CPU: The system is explicitly configured for high performance on multi-core CPUs (e.g., 22 threads) by leveraging OMP, MKL, and large batch sizes for efficient training, making it ideal for powerful workstations without dedicated GPU access.

    K-Fold Cross-Validation: Evaluates the model's robustness and generalization capability across multiple test folds, providing detailed RMSE comparisons.
