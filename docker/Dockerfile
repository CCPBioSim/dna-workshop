# Start with BioSim base image.
ARG BASE_IMAGE=latest
FROM ghcr.io/ccpbiosim/jupyterhub-base:$BASE_IMAGE

LABEL maintainer="James Gebbie-Rayet <james.gebbie@stfc.ac.uk>"

# Switch to jovyan user.
USER $NB_USER
WORKDIR $HOME

# Install workshop deps
#RUN conda install -c acellera -c conda-forge ambertools htmd=2.5.7 matplotlib mdtraj nglview numpy=2.3.5 -y
RUN conda install -y -c conda-forge -c acellera \
    conda-forge::matplotlib=3.11.2 \
    conda-forge::mdtraj=1.11.1 \
    conda-forge::numpy=2.4.6 \
    conda-forge::ambertools=24.8 \
    conda-forge::nglview=4.0.1 \
    conda-forge::ipywidgets=8.1.9 \
    acellera::htmd

COPY docker/fix-nglview.sh /tmp/fix-nglview.sh
RUN bash /tmp/fix-nglview.sh

# Get workshop files and move them to jovyan directory.
COPY --chown=1000:100 . .
RUN rm -rf requirements.txt LICENSE README.md docker .git .github tested_files

RUN wget https://file-store.ccpbiosim.org/tw2025-dna-workshop/01_Prod-0.nc && \
    mv 01_Prod-0.nc data/

# Copy updated lab workspace
COPY --chown=1000:100 docker/default-37a8.jupyterlab-workspace /home/jovyan/.jupyter/lab/workspaces/default-37a8.jupyterlab-workspace

# Always finish with non-root user as a precaution.
USER $NB_USER
