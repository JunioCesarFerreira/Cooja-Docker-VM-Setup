# Simulação Contiki-NG com Cooja

🌍 *[English](README.md)*

Este exemplo contém código de simulação do Contiki-NG para avaliação de desempenho de rede e consumo de energia usando o simulador Cooja.

## Visão Geral do Projeto

O projeto consiste em duas principais aplicações do Contiki-NG:

1. **Cliente UDP**: Um nó que envia periodicamente pacotes contendo métricas de desempenho da rede e consumo de energia.
2. **Servidor UDP**: Um nó que recebe os pacotes e registra as métricas.

Essas aplicações utilizam IPv6 sobre TSCH para comunicação e fazem uso do módulo Energest para medir o consumo de energia.

## Funcionalidades

- Comunicação UDP entre cliente e servidor.
- Monitoramento do consumo de energia (CPU, LPM, Rádio TX, Rádio RX).
- Estatísticas de latência e transmissão de pacotes.
- Manipulação de endereços IPv6 e registro de pacotes.

## Estrutura de Arquivos

- `udp-client.c`: Implementação do cliente UDP.
- `udp-server.c`: Implementação do servidor UDP.
- `send-vm.py`: Script para transferir arquivos-fonte para a máquina virtual.
- `fetch-vm.py`: Script para recuperar arquivos XML de simulação (`.csc`) e arquivos de posição dos nós.
- `send-docker.py`: Script para transferir arquivos para o contêiner Docker.
- `fetch-docker.py`: Script para recuperar logs de simulação.

## Fluxo de Uso

### Usando uma Máquina Virtual
1. Escreva ou modifique os arquivos C no diretório de trabalho.
2. Certifique-se de que a VM está em execução. [Veja como configurar](https://github.com/JunioCesarFerreira/Cooja-Docker-VM-Setup/blob/main/vm/prepare-vm-enviroment.md).
3. Use `send-vm.py` para transferir os arquivos para a VM.
4. Execute a interface gráfica do Cooja dentro da VM para testar as simulações.
5. Use `fetch-vm.py` para recuperar os resultados da simulação (`.csc` e `Positions.dat`).

### Usando um Contêiner Docker
1. Certifique-se de que o contêiner está em execução. [Veja como configurar](https://github.com/JunioCesarFerreira/Cooja-Docker-VM-Setup/tree/main/ssh-docker-cooja).
2. Use `send-docker.py` para transferir arquivos para o contêiner.
3. Conecte-se ao contêiner via SSH.
4. Execute o Cooja no modo sem interface gráfica:
   ```sh
   java --enable-preview -Xms4g -Xmx4g -jar build/libs/cooja.jar --no-gui simulation.csc > sim.log
   ```
5. Use `fetch-docker.py` para recuperar os logs da simulação.

### Gerenciamento de Posições
O [notebook](positions-mngmt.ipynb) fornece ferramentas para gerar e visualizar posições dos nós nas simulações, além de criar os arquivos `positions.dat` e `simulation.xml` para configurar os ambientes de simulação, incluindo cenários com mobilidade simples.

## Dependências

- Contiki-NG
- Simulador Cooja
- Python (para scripts de automação)
- Docker (se executado em ambiente conteinerizado)
- Oracle VM VirtualBox (se executado em uma VM Ubuntu)
- WSL (para usuários Windows)
- VS Code (para edição de código)