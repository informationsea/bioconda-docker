FROM debian:10-slim
RUN apt-get update -y && apt-get install -y curl && apt-get clean -y && \
    curl -OL https://repo.anaconda.com/miniconda/Miniconda2-latest-Linux-x86_64.sh && \
    mkdir -p /root/.conda && bash ./Miniconda2-latest-Linux-x86_64.sh -b -p /opt/miniconda2 && \
    rm ./Miniconda2-latest-Linux-x86_64.sh && \
    /opt/miniconda2/bin/conda config --add channels defaults && \
    /opt/miniconda2/bin/conda config --add channels bioconda && \
    /opt/miniconda2/bin/conda config --add channels conda-forge
ENV PATH /opt/miniconda2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ADD run.sh /
ENTRYPOINT [ "/bin/bash", "/run.sh" ]
