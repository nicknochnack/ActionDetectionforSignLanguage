# Action Detection for Sign Language
---
This repository houses work that follows a tutorial presented on [YouTube](https://www.youtube.com/watch?v=doDUihpj6ro&t=4444s)
by Nicholas Renotte. I am not the original author, I am simply trying to enable people to have a working, reproducible
environment that runs the code. Because I do not have a camera, I cannot make use of `cv2` functionality early on in the
notebook to generate a variable called `frame`. Best of luck! What I can say is that the initial imports run successfully, as
well as some of the first several notebook cells. Presumably, the package installs that were at the top of the first notebook,
and now removed, were all that were necessary for successful execution.

Because the intended/target audience is probably less saavy, I will be descriptive regarding how to get this running.

In order to follow along, you will want to do the following:

1. Ensure that you have a `python 3.8` environment installed. For example:

```bash
conda create -n your_env_name python=3.8
```

2. Activate that conda environment:

```bash
conda activate your_env_name
```

3. Pip install the repository:

```bash
pip install -e .
```

4. Once this is done, you can run:

```bash
jupyter lab
```

Which will spin up a `jupyter lab` server on your local host, and from there, you should be off and running.

**NOTE**: If it doesn't work immediately, make sure your notebook is using the appropriate conda environment.
It should default to the currently active env.