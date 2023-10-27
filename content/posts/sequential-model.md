---
title: "Sequential Model"
date: 2023-10-24T14:43:53+11:00
draft: false
---

# Introduction

For general sequence modeling, the probability of transitioning to the next state could potentially depend on all previous states:

$$
P(X_{n+1} = x | X_1 = x_1, X_2 = x_2, \ldots , X_n = x_n)
$$

# First Order Markov Assumption

The first-order Markov assumption states that the probability of transitioning to the next state depends only on the current state and not on the sequence of states that preceded it.

$$
P(X_{n+1} = x | X_1 = x_1, X_2 = x_2, \ldots , X_n = x_n) = P(X_{n+1} = x | X_n = x_n)
$$

## Auto Regressive Model

### Recurrent Neural Network (RNN)

RNN is designed to recognise pattern in sequences of data by sharing the parameters for each data cross time index

$$
h_t = \sigma(W_x X_t + W_h h_{t-1} + b)
$$

- $ h_t $: Hidden state at time \( t \).
- $ \sigma $: Activation function (often the hyperbolic tangent or sigmoid).
- $ W_x $: Weight matrix for the current input \( X_t \).
- $ X_t $: Input at time \( t \).
- $ W_h $: Weight matrix for the previous hidden state \( h\*{t-1} \).
- $ h\_{t-1} $: Hidden state at the previous time step \( t-1 \).
- $ b $: Bias term.

### Long Short-Term Memory (LSTM)

LSTM consists of

- Forget Gate: It controls the proportion of information in long-term memory to be carried forward (sigmoid)
- Input Gate: (tanh and sigmoid)
- Output Gate: It controls the proportion of information in long-term memory to be carried forward to next short-term memory (sigmoid)

$$
C_t = f_t \odot C_{t-1} + i_t \odot \tanh(W_{C} [h_{t-1}, X_t] + b_C)
$$

- $ C_t $: Cell state at time \( t \).
- $ f_t $: Activation of the forget gate at time \( t \).
- $ C\_{t-1} $: Cell state at the previous time step \( t-1 \).
- $ i_t $: Activation of the input gate at time \( t \).
- $ W_C $: Weight matrix for the combined previous hidden state and current input.
- $ h\_{t-1} $: Hidden state at the previous time step \( t-1 \).
- $ X_t $: Input at time \( t \).
- $ b_C $: Bias term for the cell state.

### Gated Recurrent Unit (GRU)

$$
h_t = (1 - z_t) \odot h_{t-1} + z_t \odot \tilde{h}_t
$$

- $ h_t $: Hidden state at time \( t \).
- $ z_t $: Activation of the update gate at time \( t \).
- $ h\_{t-1} $: Hidden state at the previous time step \( t-1 \).
- $ \tilde{h}\_t $: Candidate activation for the hidden state at time \( t \).

## Training the Models

- The number of timesteps must be the same within a single batch

## Inference

- RNNs can inference data of any sequence length
