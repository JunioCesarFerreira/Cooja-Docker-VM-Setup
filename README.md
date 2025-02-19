# **Cooja Docker VM Setup**

Elementary scripts for running the [Contiki-NG](https://github.com/contiki-ng/contiki-ng)'s [Cooja](https://github.com/contiki-ng/cooja) simulator using Docker containers. In this repository we also show how to setup a VM for use with Cooja.

## About the Current Version

- [SSH Cooja environment](./ssh-docker-cooja): This is the main object of this repository. How to build a docker image for use with cooja via SSH. Useful for large-scale simulations. Docker image available on [DockerHub](https://hub.docker.com/repository/docker/juniocesarferreira/simulation-cooja/general).

- [Test Terminal Docker Cooja](./test-docker-cooja): This is the project for testing and implementing new features in the Cooja container. Docker image available on [DockerHub](https://hub.docker.com/repository/docker/juniocesarferreira/docker-cooja/general).

## Using Cooja with a Virtual Machine (VM)

To use the Cooja GUI and handle simulations, you can set up a Virtual Machine (VM). Learn how to do this [here](./vm/prepare-vm-enviroment.md).


## Using Example
This [example](./example) presents a flow for use with both a VM and a Docker Container, allowing you to exchange information between them as needed for simulations. We also include some tools to make experimentation easier. The simulation in the example uses RPL UDP with some mobile motes and with metrics collected from clients by the server.


## Contributions

Corrections and improvements are always welcome!


## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

