# Apache spark
```python
ps.read_parquet() # to read parquet files
```

# Ray
- you need to define the training logic as a function (`train_func`). You pass this [training function](https://docs.ray.io/en/latest/train/overview.html#train-overview-training-function) to the [`TorchTrainer`](https://docs.ray.io/en/latest/train/api/doc/ray.train.torch.TorchTrainer.html#ray.train.torch.TorchTrainer "ray.train.torch.TorchTrainer") to on every Ray worker. The training then proceeds using PyTorch DDP