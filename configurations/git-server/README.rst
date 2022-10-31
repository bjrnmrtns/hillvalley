======
README
======

Dockerimage which serves as a git server.
Authentication is done by copying the users public key to the git server
as authorized key. If the public key is changed the docker image
needs to be rebuild.


Prerequisites
=============
- A public key in ~/.ssh/id_ed25519.pub
- make
- Have your git repositories in ~/repos/
- The git repositories should be created userid 1000 

Build
=====
How to build the git-server docker image

::
  make build

Run
===
How to run the git-server docker image a a container

::
  make run

