# 08 - EC2 Status check

- System Status check: Harware (físco) que a máquina está sentada.
  - Tudo que está relacionado ao host físico.
  - Não é possível simular uma falha
  - Tipos de System Status Check:
    - Perda de conectividade.
    - Falha de energia.
    - Software no harware físico.
    - A melhor forma de resolver é realizando stop e start da instância.

- Instance Status check: Máquina virtual
  - Falha na checagem do status do sistema.
  - Erro de configuração de networking ou de inicialização da instancia.
  - Exaustão de memória.
  - Sistema de arquivo corrompido (SO).
  - Kernel incompatível.
  - A melhor forma de resolver é realizando o reboot da intância ou realizando modificações no sistema operacional.
