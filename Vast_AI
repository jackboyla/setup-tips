
1. Set the WANDB_API_KEY environment variable when starting the Jupyter instance; you can use the --env flag with the docker run command to set an environment variable for your API key. This will make the variable available to the onstart script.
Here's an example command:

`-e API_KEY=your-api-key`

2. Inside your onstart script, export the WANDB_API_KEY environment variable to a file that is not accessible to other users. You can do this by adding a line like the following to your onstart script:

```
echo "export WANDB_API_KEY='your-api-key'" >> /home/vastai/secrets.sh
chmod 600 /home/vastai/secrets.sh
```

This will create a file called /home/vastai/secrets.sh that contains the WANDB_API_KEY environment variable, and set its permissions to be readable only by the owner.

3. In your Jupyter notebook, you can then source the secrets.sh file to make the WANDB_API_KEY environment variable available to your Python code. You can do this by adding the following line to a cell in your notebook:

```
%env WANDB_API_KEY = !/bin/bash -c "source /home/vastai/secrets.sh && echo $WANDB_API_KEY"
```

This will set the WANDB_API_KEY environment variable in your Jupyter notebook session to the value stored in the secrets.sh file.

Then use:

```
import os

api_key = os.environ.get('API_KEY')
```


Following from [Vast FAQ](https://vast.ai/faq#Instances)
> Any environment variables you set will be visible only to your onstart script (or your entrypoint for entrypoint launch mode). When using the ssh or jupyter launch modes, your env variables will not be visible inside your ssh/tmux/jupyter session by default. To make custom environment variables visible to the shell you need to export them to /etc/environment.
