# Robust DA-DT CsiNet for Non-Ideal Feedback Channels

## Overview
This project proposes Robust DA-DT CsiNet, an enhanced CSI feedback framework designed for Massive MIMO systems operating under non-ideal feedback channels.

Key challenges addressed:
- Packet loss
- Channel noise
- Error propagation in temporal CSI reconstruction

## Research Problem
DA-DT CsiNet uses delta feedback to reduce transmission overhead, but a single lost packet can cause error accumulation and reconstruction failure in subsequent frames.

Goal:
- Mitigate sequential error propagation
- Improve CSI reconstruction robustness
- Maintain low communication overhead

## Proposed Method

### UE Side
1. Spatial Encoder (DWConv)
2. Doppler Head
3. Robust Delta Module

Key Frame:
t mod N = 0
f_t = z_t

Delta Frame:
t mod N != 0
f_t = Δz_t = z_t - ẑ_(t−1)

### Non-Ideal Feedback Channel
f_(t,received) = α_t * f_t + n_t

Where:
- α_t ∈ {0,1}: packet loss indicator
- n_t ~ N(0,σ²): channel noise

### BS Side
1. Error Recovery
2. Doppler-Aware Gated Attention
3. Decoder

## Ablation Studies
1. Periodic Key-Frame Mechanism
2. Noise Injection Training
3. Gated Attention vs Fixed Window Transformer

## Expected Results
- 4–6 dB NMSE improvement under 5% packet loss
- Error bounded within N−1 frames
- No additional UE computation overhead

## Timeline
Days 1–2: Dataset preparation and baseline reproduction
Days 3–4: Robust module implementation
Days 5–6: Training
Days 7–8: Evaluation and ablation studies
Days 9–10: Final report and presentation

## Keywords
Massive MIMO
CSI Feedback
Deep Learning
Transformer
Delta Feedback
Packet Loss
Channel Noise
Error Propagation
Doppler-Aware Attention
5G-Advanced
6G
