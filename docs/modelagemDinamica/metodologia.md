# Metodologia da Modelagem Dinâmica

---

## Sumário
- [Técnica Utilizada](#técnica-utilizada)
- [Objetivos](#objetivos)
- [Bibliografia](#bibliografia)
- [Histórico de Versões](#histórico-de-versões)

---

## Técnica Utilizada

A modelagem dinâmica foca em descrever o comportamento do sistema ao longo do tempo, capturando como seus componentes interagem e reagem a eventos internos e externos. Para o projeto "Aprendendo com IA", utilizamos um conjunto de diagramas da UML para representar essa dinâmica de forma abrangente:

1.  **[Diagrama de Sequência](modelagemDinamica/diagramaDeSequencia.md):** Utilizado para ilustrar a troca de mensagens entre objetos em uma ordem cronológica. Ele é essencial para visualizar o fluxo de controle de um caso de uso específico, como o processo de autenticação ou a submissão de uma tarefa.

2.  **[Diagrama de Atividades](modelagemDinamica/diagramaDeAtividades.md):** Empregado para modelar os fluxos de trabalho (workflows) do sistema, passo a passo. É ideal para representar a lógica de processos complexos, mostrando as ações, decisões e caminhos alternativos, como o fluxo de cadastro de um novo usuário ou a realização de um quiz.

3.  **[Diagrama de Comunicação](modelagemDinamica/diagramaDeComunicacao.md):** Focado nos relacionamentos (vínculos) entre os objetos que interagem. Diferente do diagrama de sequência, sua ênfase está na organização estrutural dos participantes da interação, e não na linha do tempo.

4.  **[Diagrama de Estados](modelagemDinamica/diagramaDeEstados.md):** Usado para descrever o ciclo de vida de um objeto, mostrando os diferentes estados em que ele pode se encontrar e as transições entre esses estados, que são disparadas por eventos. É perfeito para modelar entidades que possuem um comportamento complexo, como o estado de uma `Tarefa` (ex: "não iniciada", "em andamento", "corrigida").

A combinação desses artefatos nos permite construir uma visão completa e detalhada do comportamento do sistema, desde interações de alto nível até a lógica interna de componentes individuais.

---

## Objetivos

O principal objetivo da modelagem dinâmica neste projeto é garantir que o comportamento do sistema "Aprendendo com IA" seja bem compreendido, consistente e alinhado aos requisitos funcionais. Os objetivos específicos são:

- **Detalhar a Lógica dos Casos de Uso:** Transformar as interações descritas nos Casos de Uso em fluxos operacionais claros, mostrando como os atores e o sistema colaboram para atingir um objetivo.

- **Visualizar a Colaboração entre Componentes:** Expor como os diferentes componentes da arquitetura (definidos no Diagrama de Componentes) se comunicam para executar uma funcionalidade.

- **Validar o Comportamento do Sistema:** Servir como uma ferramenta para a equipe validar a lógica de negócio e identificar possíveis falhas, ambiguidades ou gargalos no fluxo de interação antes da fase de implementação.

- **Apoiar o Desenvolvimento e Testes:** Fornecer um guia claro para os desenvolvedores implementarem a lógica de controle e para a equipe de testes criar cenários de teste que cubram os diferentes fluxos e estados do sistema.

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data de Produção | Revisor(es) | Data de Revisão | Incremento do Revisor |
| :----: | --------- | --------- | :--------------: | ----------- | :-------------: | :-------------------: |
| `1.0`  | Modelagem inicial | [Felipe das Neves](https://github.com/FelipeFreire-gf) | 12/09/2025 |  | |  |
| `1.1`  | Desenvolvimento do documento | [Felipe das Neves](https://github.com/FelipeFreire-gf) | 22/09/2025 |  | |  |
