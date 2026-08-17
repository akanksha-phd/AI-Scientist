# PyTorch Neural Network Fundamentals

## Objective
Understand the basic PyTorch training workflow.

## What I implemented
- Tensor creation and shape manipulation
- Autograd
- Linear model with `nn.Linear`
- MSE loss
- SGD optimizer
- Training loop
- Inference with `model.eval()` and `torch.no_grad()`

## Key takeaway
A neural network learns by repeating:

forward pass → loss → backpropagation → parameter update

The simple model learned the relationship approximately:

y = 2x + 1
