# Dockerfile Bug: Missing requirements.txt

This repository demonstrates a common error in Dockerfiles: attempting to install packages from a `requirements.txt` file that doesn't exist in the context of the Docker build.

## Bug

The `Dockerfile` attempts to install Python packages using `pip3 install -r requirements.txt`. However, the `requirements.txt` file is not included in the build context. This results in a build failure.

## Solution

The `Dockerfile.fixed` file demonstrates the solution.  It ensures that the `requirements.txt` file is copied into the image before the `pip3 install` command is executed.