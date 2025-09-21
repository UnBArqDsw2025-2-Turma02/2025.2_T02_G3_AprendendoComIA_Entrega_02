# Diagrama de Estados

---

## Sumário
- [Técnica Utilizada](#técnica-utilizada)
- [Objetivos](#objetivos)
- [Bibliografia](#bibliografia)
- [Histórico de Versões](#histórico-de-versões)

---

## Técnica Utilizada
O **Diagrama de Estados** (State Machine Diagram) é um artefato da UML utilizado para representar o **comportamento dinâmico** de um sistema ou de seus componentes.  
Ele mostra os **estados possíveis** de um objeto e as **transições** entre eles, disparadas por eventos e acompanhadas de ações.  

Segundo Sommerville¹, os diagramas de estados permitem:  

> “descrever como os sistemas reagem a eventos externos e internos, modelando o ciclo de vida de objetos e subsistemas”.  

### Etapas seguidas
1. Análise dos requisitos funcionais e não funcionais levantados.  
2. Identificação dos módulos com comportamento dinâmico (Autenticação, Chat, Tarefas, SRS, Quiz, Spelling, Social Rooms, Dicionário e Personas).  
3. Definição dos estados principais de cada módulo e eventos que disparam mudanças.  
4. Construção dos diagramas no padrão UML 2.5 (utilizando a ferramenta Mermaid e posterior exportação gráfica).  

---

## Objetivos
O objetivo deste diagrama é fornecer uma visão **clara e integrada do comportamento dinâmico** do sistema. Mais especificamente:  

- Representar os **estados internos** de cada módulo e como o usuário ou o sistema disparam transições.  
- Tornar explícito o **fluxo de execução** de funcionalidades (ex.: autenticação, submissão de tarefas, revisões no SRS).  
- Apoiar o processo de **validação de requisitos** e **entendimento da lógica do sistema** por parte da equipe de desenvolvimento e docentes.  

---


## Bibliografia

- [OMG UML 2.5.1 Specification – Object Management Group](https://www.omg.org/spec/UML/2.5.1/)  
- [UML State Machine Diagrams – UML Diagrams.org](https://www.uml-diagrams.org/state-machine-diagrams.html)  
- [The Unified Modeling Language User Guide – Addison-Wesley](https://www.amazon.com/Unified-Modeling-Language-User-Guide/dp/0321267974)  
- [UML Essencial: Um breve guia para a linguagem padrão de modelagem de objetos – Bookman](https://www.amazon.com.br/UML-Essencial-Breve-Linguagem-Modelagem/dp/8577800223)  
- [State Machine Diagram Tutorial – Visual Paradigm](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-state-machine-diagram/)

---

## Histórico de Versões

| Versão | Descrição                                                        | Autor(es)                                              | Data de Produção | Revisor(es) | Data de Revisão | Incremento do Revisor |
| :----: | ---------------------------------------------------------------- | ------------------------------------------------------ | :--------------: | ----------- | :-------------: | :-------------------: |
|  `1.0` | Modelagem inicial | [Leonardo de Melo Lima](https://github.com/leozinlima), [Mateus Bastos](https://github.com/MateuSansete) |    21/09/2025    |             |                 |                       |