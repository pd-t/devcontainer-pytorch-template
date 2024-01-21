# Devcontainer Template for PyTorch with CUDA Support

Welcome to this repository, serving as a streamlined example to demonstrate a Devcontainer implementation with PyTorch and CUDA support. Utilizing Poetry for package management, this setup ensures an efficient installation process within the working directory under .venv. This enables the execution of both Python scripts with CUDA support (see app/check_cuda.py) and Jupyter notebooks (see notebooks/check_cuda), harnessing the full power of PyTorch with GPU acceleration.

## Getting Started
### Prerequisites

A local or remote machine equipped with a GPU. Nvidia Container Toolkit installed (Installation Guide). Personal Access Token for read and write access to your repository.

### Clone the Repository

Fork this repository and clone it to your local system. 

Setup GitHub Access To enable pushing changes back to your repository, create a devcontainer.env file in the .devcontainer folder and input your Personal Access Token:

``` bash
GITHUB_TOKEN="<YOUR_GITHUB_TOKEN>"
```

If you're working on a remote machine or your Git configuration doesn't automatically sync with the devcontainer, you can also store your Git author name and email here:

```bash
GIT_AUTHOR_NAME="<YOUR NAME>"
GIT_AUTHOR_EMAIL="<YOUR EMAIL ADDRESS>"
```

Additionally, this devcontainer.env file can be used to securely store other credentials, such as S3 access keys.
Start the Container

### Check CUDA support
Everything is now set up for you to start the Devcontainer. Now, execute the Python script (see app/check_cuda.py) or the Jupyter notebook (see notebooks/check_cuda) and check CUDA support.

## Tips & Tricks

In case of extended operations, you can modify the following line in devcontainer.json to prevent automatic shutdown:

``` json
    //"shutdownAction": "none",
```

This prevents the Devcontainer from shutting down when the connection is lost, which is particularly useful for long-duration tasks like training neural networks. Combine this feature with tools like screen or tmux for uninterrupted computing sessions.
