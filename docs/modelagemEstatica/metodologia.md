# Metodologia da Modelagem Estática

---

## Sumário
- [Técnica Utilizada](#técnica-utilizada)
- [Objetivos](#objetivos)
- [Bibliografia](#bibliografia)
- [Histórico de Versões](#histórico-de-versões)

---

## Técnica Utilizada

A modelagem estática foca em descrever a estrutura do sistema, seus componentes e os relacionamentos entre eles, sem considerar o comportamento dinâmico ao longo do tempo. Para o projeto "Aprendendo com IA", utilizamos três diagramas UML que, juntos, fornecem uma visão completa da arquitetura:

1.  **[Diagrama de Classes](modelagemEstatica/diagramaDeClasses.md):** Utilizado para representar a estrutura fundamental do sistema. Ele detalha as classes, seus atributos, métodos e os relacionamentos (associação, herança, dependência), servindo como um blueprint para o código-fonte. Responde à pergunta: "Quais são os blocos de construção do software e como eles se conectam?".

2.  **[Diagrama de Componentes](modelagemEstatica/diagramaDeComponentes.md):** Empregado para mostrar a organização e as dependências entre os componentes de software de alto nível, como bibliotecas, executáveis e APIs. Ele ilustra a arquitetura modular do sistema, focando em como as partes do software são divididas e interagem. Responde à pergunta: "Como o sistema é dividido em partes substituíveis?".

3.  **[Diagrama de Implantação](modelagemEstatica/diagramaDeImplantacao.md):** Usado para modelar a disposição física do sistema, mostrando como os componentes de software são distribuídos nos nós de hardware (servidores, dispositivos). Ele é essencial para planejar a infraestrutura e entender o ambiente de execução. Responde à pergunta: "Onde o software será executado?".

A combinação desses artefatos oferece uma visão que vai desde a estrutura lógica do código até a sua implantação física, garantindo uma base sólida para o desenvolvimento e a manutenção do sistema.

---

## Objetivos

O principal objetivo da modelagem estática é definir e comunicar a arquitetura do sistema "Aprendendo com IA" de forma clara e não ambígua. Os objetivos específicos são:

- **Definir a Estrutura do Domínio:** Mapear as entidades de negócio (Usuário, Tarefa, Chat, etc.) e seus relacionamentos, garantindo que o software reflita corretamente as regras do problema.
- **Ilustrar a Arquitetura de Software:** Apresentar a divisão do sistema em componentes (Frontend, Backend, Banco de Dados) e como eles se comunicam, facilitando o planejamento e a distribuição de trabalho.
- **Planejar a Infraestrutura Física:** Especificar o hardware e a topologia de rede onde o sistema será implantado, apoiando as decisões de DevOps e gerenciamento de infraestrutura.
- **Servir como Guia para o Desenvolvimento:** Fornecer um modelo visual detalhado que orienta os desenvolvedores na implementação das classes, componentes e configurações, reduzindo inconsistências e retrabalho.

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data de Produção | Revisor(es) | Data de Revisão | Incremento do Revisor |
| :----: | --------- | --------- | :--------------: | ----------- | :-------------: | :-------------------: |
| `1.0`  | Modelagem inicial | [Felipe das Neves](https://github.com/FelipeFreire-gf) | 12/09/2025 |  | |  |
| `1.1`  | Desenvolvimento do documento | [Felipe das Neves](https://github.com/FelipeFreire-gf) | 22/09/2025 |  | |  |
