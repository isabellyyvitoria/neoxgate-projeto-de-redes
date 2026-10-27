
# Documentação Técnica — Projeto NeoxGate

**Autoria:** Isabelly Santos  
**Área de atuação:** Firewall da Matriz  
**Contexto:** Projeto acadêmico desenvolvido no SENAI em parceria com a empresa CTI.

---

## 1. Apresentação do Projeto

A NeoxGate é um projeto acadêmico de infraestrutura de redes desenvolvido com o objetivo de planejar e prototipar uma estrutura de rede para um cenário empresarial.

O projeto considera a organização de uma matriz e uma filial, abordando conceitos de segurança, segmentação de rede, comunicação entre ambientes e administração da infraestrutura.

Esta documentação apresenta uma visão geral do projeto e detalha principalmente minha participação na configuração do firewall da matriz.

## 2. Objetivos

O projeto busca aplicar conhecimentos de redes de computadores e segurança da informação em um cenário empresarial simulado.

Entre os principais conceitos abordados estão:

- Segmentação de rede;
- Configuração e gerenciamento de firewall;
- Endereçamento IPv4;
- Distribuição automática de endereços IP por DHCP;
- Organização da infraestrutura da matriz e da filial;
- Planejamento da comunicação entre segmentos de rede.

Os recursos planejados devem ser diferenciados daqueles efetivamente configurados e testados durante o desenvolvimento.

## 3. Arquitetura da Rede

A arquitetura da NeoxGate considera dois ambientes principais: matriz e filial. Os diagramas desenvolvidos pela equipe representam a organização proposta para a infraestrutura.

### 3.1 Arquitetura Geral

![Arquitetura da NeoxGate](../images/Arquitetura-Neoxgate.png)

### 3.2 Diagrama do Protótipo — Matriz

![Diagrama do protótipo da matriz](../images/Diagrama%20do%20prot%C3%B3tipo%20-%20Matriz.jpg)

### 3.3 Segmentação de Rede

A segmentação de rede consiste em dividir uma infraestrutura em segmentos lógicos, facilitando a organização dos dispositivos e a aplicação de regras de comunicação.

No projeto, esse conceito faz parte do planejamento da infraestrutura. Os IDs das VLANs, endereços IP, gateways e políticas correspondentes devem ser documentados conforme as configurações efetivamente realizadas e validadas.

## 4. Tecnologias e Conceitos Utilizados

- **FortiGate:** equipamento de segurança utilizado no laboratório;
- **FortiOS:** sistema operacional do firewall;
- **IPv4:** endereçamento utilizado para identificar interfaces e dispositivos;
- **DHCP:** serviço responsável pela distribuição automática de configurações IP;
- **VLANs:** recurso de segmentação lógica de redes;
- **Topologia de rede:** representação dos componentes e de suas conexões.

## 5. Minha Participação — Firewall da Matriz

Minha responsabilidade no projeto foi trabalhar na configuração do firewall da matriz, utilizando um equipamento FortiGate 40F.

### 5.1 Identificação do Equipamento

| Item | Informação |
|---|---|
| Equipamento | FortiGate 40F |
| Sistema operacional | FortiOS 7.4.12, build 2902 |
| Hostname | `FGT-VDOM-MTZ-SENAI` |
| VDOM registrado | `NEOXGATE` |
| Modo de operação | NAT |

### 5.2 Configuração das Interfaces

As interfaces foram organizadas para atender às funções de rede interna e conexão WAN.

| Interface | Alias | Configuração | Endereço |
|---|---|---|---|
| `lan1` | LAN | IP estático | `192.168.200.1/24` |
| `lan2` | WAN | DHCP | Endereço recebido por DHCP |

A interface `lan1` foi configurada com endereço IP estático para atuar como interface da rede interna. A interface `lan2` foi configurada para receber seu endereço IP por DHCP.

### 5.3 Configuração do DHCP

Foi configurado um servidor DHCP associado à interface `lan1`, permitindo a distribuição automática de endereços IP aos dispositivos clientes.

| Parâmetro | Valor |
|---|---|
| Interface | `lan1` |
| Faixa inicial | `192.168.200.2` |
| Faixa final | `192.168.200.254` |
| Gateway | `192.168.200.1` |

Essa configuração permite que os dispositivos conectados à rede recebam automaticamente seus parâmetros de endereçamento, conforme as definições do servidor DHCP.

### 5.4 Gerenciamento do Firewall

Durante o laboratório, foram utilizados o console e a interface web para acessar e administrar o equipamento.

O acesso administrativo depende da conectividade com a interface configurada, do endereço utilizado e dos serviços de gerenciamento habilitados.

As configurações finais de acesso devem ser registradas após a validação do ambiente. Credenciais, senhas e chaves de acesso não devem ser incluídas nesta documentação.

### 5.5 VLANs e Políticas de Firewall

As VLANs e as políticas de firewall devem ser documentadas conforme forem configuradas e testadas.

Para cada configuração, é importante registrar:

- Objetivo da regra ou segmento;
- Interface envolvida;
- Redes de origem e destino;
- Serviços permitidos;
- Ação aplicada;
- Resultado dos testes.

Somente configurações efetivamente realizadas devem ser descritas como concluídas.

## 6. Testes e Validações

Os testes são importantes para verificar se as configurações estão funcionando conforme o esperado.

| Teste | Status |
|---|---|
| Acesso administrativo ao FortiGate | A validar |
| Conectividade com o gateway `192.168.200.1` | A validar |
| Distribuição de endereços via DHCP | A validar |
| Comunicação entre VLANs | A validar |
| Aplicação das políticas de firewall | A validar |

Os resultados devem ser atualizados de acordo com os testes realmente executados. Caso sejam obtidas capturas de tela ou saídas de comandos, elas poderão ser utilizadas como evidências técnicas, desde que autorizadas para publicação.

## 7. Dificuldades Encontradas

Durante a configuração de equipamentos de rede, podem ocorrer dificuldades relacionadas à conectividade, ao acesso administrativo e à validação das configurações.

Nesta seção, serão registradas as dificuldades efetivamente encontradas durante o projeto, incluindo:

1. Descrição do problema;
2. Procedimentos utilizados para investigar a causa;
3. Solução aplicada;
4. Testes realizados após a correção.

## 8. Aprendizados

O desenvolvimento desta parte do projeto contribui para o aprendizado prático sobre configuração de firewall, endereçamento IPv4, DHCP, interfaces de rede e gerenciamento de equipamentos de segurança.

A atividade também reforça a importância de documentar as alterações realizadas e validar o funcionamento da infraestrutura por meio de testes.

Esta seção poderá ser complementada com os aprendizados específicos obtidos durante as próximas etapas do projeto.

## 9. Conclusão

Minha participação na NeoxGate foi direcionada à configuração do firewall da matriz, incluindo o registro das configurações das interfaces LAN e WAN e do serviço DHCP da rede interna.

O desenvolvimento do projeto permite aplicar conceitos estudados no curso de Redes de Computadores em um cenário prático, aproximando o planejamento da infraestrutura das atividades de configuração e validação de equipamentos.

Esta documentação será atualizada conforme as configurações forem concluídas, os testes forem realizados e novas evidências técnicas puderem ser registradas.

## 10. Segurança e Publicação

Antes de publicar informações relacionadas ao projeto, é necessário confirmar que a equipe e a empresa autorizam o compartilhamento dos materiais.

Não devem ser publicados:

- Senhas e credenciais;
- Chaves privadas ou tokens;
- Informações pessoais;
- Dados internos ou confidenciais da empresa;
- Capturas de tela que exponham informações sensíveis.

Diagramas e demais materiais devem ser publicados somente quando houver autorização para compartilhamento.
