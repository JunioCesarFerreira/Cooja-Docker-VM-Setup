# **Configuração de Cooja com Docker e Máquina Virtual (VM)**

🌍 *[English](README.md)*

Scripts básicos para executar o simulador [Cooja](https://github.com/contiki-ng/cooja) do [Contiki-NG](https://github.com/contiki-ng/contiki-ng) usando contêineres Docker. Neste repositório, também mostramos como configurar uma máquina virtual (VM) para uso com o Cooja.

## Sobre a Versão Atual

- [Ambiente SSH para Cooja](./ssh-docker-cooja): Este é o principal objetivo deste repositório. Explicamos como criar uma imagem Docker para uso com o Cooja via SSH, útil para simulações em larga escala. A imagem Docker está disponível no [DockerHub](https://hub.docker.com/repository/docker/juniocesarferreira/simulation-cooja/general).

- [Teste do Terminal Docker Cooja](./test-docker-cooja): Projeto para testar e implementar novas funcionalidades no contêiner do Cooja. A imagem Docker está disponível no [DockerHub](https://hub.docker.com/repository/docker/juniocesarferreira/docker-cooja/general).

## Usando o Cooja com uma Máquina Virtual (VM)

Para utilizar a interface gráfica do Cooja e gerenciar simulações, você pode configurar uma Máquina Virtual (VM). Saiba como fazer isso [aqui](./vm/prepare-vm-enviroment.md).

## Exemplo de Uso

Este [exemplo](./example) apresenta um fluxo de uso tanto com uma VM quanto com um contêiner Docker, permitindo a troca de informações entre eles conforme necessário para as simulações. Também incluímos algumas ferramentas para facilitar a experimentação. A simulação do exemplo utiliza RPL UDP com alguns motes móveis, coletando métricas dos clientes por meio do servidor.

## Contribuições

Correções e melhorias são sempre bem-vindas!

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](./LICENSE) para mais detalhes.
