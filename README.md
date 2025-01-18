# Uncommon Dockerfile Errors and Solutions

This repository demonstrates a common mistake in Dockerfiles and offers a robust solution.

## Problem
The provided `Dockerfile` uses the `ubuntu:latest` image, which is generally discouraged due to potential unexpected changes between releases. It also installs Python and then runs a simple HTTP server without cleanup or consideration for production environments.

## Solution
The solution provided in `DockerfileSolution.txt` addresses these concerns by:

1. Specifying a specific Ubuntu version for reproducibility.
2. Using a more optimized approach for running a web server if that's the intention. Consider using something like Gunicorn with Nginx or Apache.
3. Cleaning up after the `apt-get install` to reduce the image size.
4. Exposing port 8000 for external access.

## How to Run

1. Clone the repo:
   `git clone <repository_url>`
2. Navigate to the directory: `cd uncommon-dockerfile-errors`
3. Build the image (using the solution Dockerfile): `docker build -t my-app .`
4. Run the container: `docker run -p 8000:8000 my-app`