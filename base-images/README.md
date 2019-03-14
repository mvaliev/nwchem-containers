# NWChem base images

Collection of NWChem dockerfiles:

* [Dockerfile.ubuntu.mpich](https://github.com/mvaliev/nwchem-containers/blob/master/base-images/Dockerfile.ubuntu.mpich)
NWChem-6.8.1 built on ubuntu:16.04 using mpich

## Instructions

Taking example dockerfile as [Dockerfile.ubuntu.mpich](https://github.com/mvaliev/nwchem-containers/blob/master/base-images/Dockerfile.ubuntu.mpich), the container tagged "nwchem-ubuntu" can be built as 

docker build -t nwchem-ubuntu -f Dockerfile.ubuntu.mpich .

Assuming that input file (e.g. [h20.nw](https://github.com/nwchemgit/nwchem/blob/master/QA/tests/h2o/h2o.nw)) is in the current directory, it can be ran as

docker container run -v $(pwd):/simulation nwchem-ubuntu mpirun -np 2 nwchem h2o.nw
