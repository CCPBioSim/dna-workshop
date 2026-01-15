# CCPBioSim DNA Workshop

[![ci](https://github.com/ccpbiosim/dna-workshop/actions/workflows/build.yaml/badge.svg?branch=main)](https://github.com/ccpbiosim/dna-workshop/actions/workflows/build.yaml)
[![latest](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fccpbiosim.github.io%2Fworkshop.json&query=%24.containers.dna-workshop.latest&labelColor=grey&logo=github&logoColor=white&label=latest&color=purple)](https://github.com/ccpbiosim/dna-workshop/pkgs/container/dna-workshop)
[![issues](https://img.shields.io/github/issues/ccpbiosim/dna-workshop?logo=github&labelColor=grey)](https://github.com/CCPBioSim/dna-workshop/issues)
[![pr](https://img.shields.io/github/issues-pr/ccpbiosim/dna-workshop?logo=github&labelColor=grey)](https://github.com/CCPBioSim/dna-workshop/pulls)

This workshop source repository contains the build recipe for a docker container derived from the CCPBioSim JupyterHub image. This container adds the necessary software packages and notebook content to form a deployable course container.

This workshop is a hands-on exercise to (a) setup a DNA + ligand simulation in explicit solvent; (b) run molecular dynamics using AMBER MD engine and (c) Visualise the trajectory using a viewer.

The workshop illustrates:

1. The use of jupyter-notebook (https://jupyter.org/)
2. The use of Python HTMD (https://software.acellera.com/docs/latest/htmd/index.html)
3. The use of Amber simulation (www.ambermd.org) and Ambertools
4. The use of nglviewer (www.nglviewer.org)
5. The use of Python MDtraj module (www.mdtraj.org)

## How to Use

This training course is deployed on the [CCPBioSim](www.ccpbiosim.ac.uk) website via our cloud infrastructure, however you can deploy on your own machine with docker.

Pull the container from our repository::

    docker pull ghcr.io/ccpbiosim/dna-workshop:latest

In our containers we are using the JupyterHub default port 8888, so you should
forward this port when deploying locally::

    docker run -p 8888:8888 ghcr.io/ccpbiosim/dna-workshop:latest

## Authors

Workshop Content Authors:

- Shozeb Haider

## Contact

Please direct all questions and feedback to [Shozeb Haider](mailto:shozeb.haider@ucl.ac.uk)
