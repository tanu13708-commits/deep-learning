# 10 — Deep Learning Summary

## Core Training Loop

```text
Input → Forward Pass → Prediction → Loss → Backpropagation
→ Gradients → Optimizer → Updated Weights → Repeat
```

## Neural Network

**z = Wx + b**

**output = f(z)**

- W = weights
- b = bias
- f = activation

## Activation Functions

| Function | Common use |
|---|---|
| Sigmoid | Binary probability output |
| Tanh | Zero-centered activation |
| ReLU | Common hidden-layer activation |
| Leaky ReLU | ReLU variant with negative slope |
| GELU | Common in modern Transformers |
| Softmax | Multi-class probability output |

## Optimization

**θ ← θ − η∇L**

- SGD → basic gradient updates
- Momentum → accumulated direction
- RMSProp → adaptive scaling from squared gradients
- Adam → first/second moment based adaptive updates

## Loss Functions

| Task | Common loss |
|---|---|
| Regression | MSE / MAE / Huber |
| Binary classification | Binary Cross-Entropy |
| Multi-class classification | Categorical Cross-Entropy |
| Multi-label classification | Binary Cross-Entropy per label |

## Regularization

Dropout, weight decay, early stopping, data augmentation, appropriate model size, and transfer learning can improve generalization.

## CNN

```text
Image → Convolution → Activation → Pooling/Stride
→ Feature Extraction → Prediction Head
```

CNNs exploit local connectivity and shared weights.

## RNN → LSTM → GRU

- RNN → recurrent hidden state
- LSTM → gates + cell state for longer dependencies
- GRU → simpler gated recurrent architecture

## Attention

**Attention(Q,K,V) = softmax(QKᵀ / √dₖ)V**

Q = Query, K = Key, V = Value.

## Transformer

```text
Input → Embedding → Positional Information → Self-Attention
→ Feed-Forward Network → Repeated Blocks → Output
```

Transformers model relationships between positions and allow highly parallel training.

## Transfer Learning

**Feature extraction:** freeze pretrained backbone + train a new head.

**Fine-tuning:** unfreeze some/all layers and continue training with suitable learning rates.

## Debugging Checklist

### Loss does not decrease
- Check data and labels
- Check output/loss compatibility
- Check learning rate
- Check gradients and parameter updates
- Check optimizer
- Try overfitting a tiny batch

### Training accuracy high, validation accuracy low
- Suspect overfitting
- Check leakage and train/validation distribution
- Use augmentation/regularization
- Check model capacity and data quality

### GPU memory insufficient
- Smaller batch/input
- Mixed precision
- Gradient accumulation
- Smaller model
- Gradient checkpointing

## Interview Strategy

**Definition → Intuition → Formula/Architecture → Example → Practical use**

Be able to explain not only **what** a technique is, but also **why it exists, what problem it solves, and when you would use it**.
