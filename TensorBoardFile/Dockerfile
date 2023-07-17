FROM pytorch/pytorch:2.0.0-cuda11.7-cudnn8-devel

# upgrade and get some module
RUN apt-get update &&\
    apt-get -y upgrade &&\
    apt-get install -y git net-tools vim sudo tcsh gcc g++ unzip python3 python3-pip &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/*

RUN pip3 --no-cache-dir install torch \
    torchvision \
    torchaudio \
    tensorboard \
    jupyterlab \
    notebook

USER ${UserName}
WORKDIR /home/${UserName}

CMD ["tensorboard", "--logdir", "./log", "--host=0.0.0.0", "--port=7772"]

EXPOSE 7772
