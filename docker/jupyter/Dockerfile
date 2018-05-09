FROM jupyter/datascience-notebook:latest
MAINTAINER chapmanbe <brian.chapman@utah.edu>
USER root
# for physionet instructions see
# https://www.physionet.org/physiotools/wfdb-linux-quick-start.shtml
# dependencies for spell nbextensions (including spell check) and other requirements

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
      tree \
      graphviz\ 
      less \
  && rm -rf /var/lib/apt/lists/*


WORKDIR /home/jovyan

# Set default editor to vim
RUN update-alternatives --set editor /usr/bin/vim.basic

USER jovyan


RUN pip install neo4j-driver \
    pydotplus \
    pyorient

# RUN nbstripout --install
CMD ["start-notebook.sh"]
