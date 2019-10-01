FROM debian:10-slim
RUN apt-get update -y && apt-get install -y curl && apt-get clean -y && \
    curl -OL https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    mkdir -p /root/.conda && bash ./Miniconda3-latest-Linux-x86_64.sh -b -p /opt/miniconda3 && \
    rm ./Miniconda3-latest-Linux-x86_64.sh && \
    /opt/miniconda3/bin/conda config --add channels defaults && \
    /opt/miniconda3/bin/conda config --add channels bioconda && \
    /opt/miniconda3/bin/conda config --add channels conda-forge
ENV PATH /opt/miniconda3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ADD run.sh /
ENTRYPOINT [ "/bin/bash", "/run.sh" ]
