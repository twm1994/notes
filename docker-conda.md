[source](https://hub.docker.com/u/continuumio)

[docker as non-root user](https://docs.docker.com/engine/install/linux-postinstall/)

sudo usermod -aG docker $USER

docker run -i -t -p 8888:8888 continuumio/conda-ci-linux-64-python3.8 /bin/bash -c "/opt/conda/bin/conda install jupyter -y --quiet && mkdir /opt/notebooks && /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser"

### R install in conda
```bash
conda create -n r_env r-essentials r-base

conda activate r_env

conda install -c conda-forge notebook

jupyter notebook --notebook-dir /home/test_user//notebooks/ --port=8888 --no-browser --ip='*'
```
