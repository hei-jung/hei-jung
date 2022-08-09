## Install & set up

```console
$ pip install wandb
$ wandb login
```

## Use

```python
import wandb

wandb.init(name="experiment-name", project="directory-name")
wandb.config = {
  "learning_rate": 0.001,
  "epochs": 100,
  "batch_size": 128
}
wandb.log({"loss": loss})

# Optional
wandb.watch(model)
```
