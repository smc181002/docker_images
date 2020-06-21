# docker_images

This image has the source code of following images
- ssh
  - This image has openssh server and client application. 
  - The root passord is `passwd@123`

- docker_enabled
  - This image has the ability to run docker commands.
  - the commands you run are executed in the host OS.
  - If the commands are not working, run `export DOCKER_HOST=<your_ip:4243>`
- jenkins
  - It is a normal jenkins file built on centos
