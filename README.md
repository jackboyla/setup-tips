# Tips when getting set up on VS Code, WandB, etc (WINDOWS)

Add conda to PATH if not already done: https://stackoverflow.com/a/51996934

NOTE: You may need to change `Select Default Profile` in VS Code to `cmd` instead of Powershell

Login to wandb via CLI: `wandb login YOUR_API_KEY`

```
!SET WANDB_API_KEY="YOUR_KEY"

# Only if you haven't logged in on CLI:
# import wandb
# wandb.login()

from pytorch_lightning.loggers import WandbLogger

wandb_logger = WandbLogger(project='sentiment-analysis')
```
