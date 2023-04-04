# Description
This project contains the code for the tutorial on docker integration in python environments

## Installation

- Docker is required to rebuild the environment

first build the image from the dockerfile

```
docker build -t <project_name>_image .
```

# Usage
Then run the container mapping ports and folder

```
docker run -i -t -p 8888:8888 -v "$PWD":/home --name <project_name>analysis <project_name>_image
```

To create a running jupyter notebook kernel to connect to use the following lines in the container shell

```
conda activate <conda_environment_name>
jupyter notebook --ip='0.0.0.0' --port=8888 --no-browser --allow-root --notebook-dir=/home
```

