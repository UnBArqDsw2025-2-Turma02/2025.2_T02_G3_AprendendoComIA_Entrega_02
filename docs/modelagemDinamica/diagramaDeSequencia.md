# Diagrama de Sequência

---

## Sumário
- [Técnica Utilizada](#técnica-utilizada)
- [Objetivos](#objetivos)
- [Bibliografia](#bibliografia)
- [Histórico de Versões](#histórico-de-versões)

---

## Técnica Utilizada

O **Diagrama de Caso de Uso** é uma ferramenta da UML (Unified Modeling Language) utilizada para representar as funcionalidades de um sistema do ponto de vista do usuário. Ele descreve as interações entre os **atores** (usuários ou sistemas externos) e o sistema, detalhando as ações que podem ser executadas.

Para o projeto "AprendendoComIA", este diagrama foi escolhido por sua capacidade de oferecer uma visão clara e de alto nível sobre:
- **O que** o sistema faz (escopo funcional).
- **Quem** interage com o sistema.
- **Como** as funcionalidades se relacionam entre si.

A modelagem visualiza as principais jornadas do usuário, desde o primeiro contato como visitante até as interações complexas de um aluno engajado, como o chat com o tutor de IA e a participação em atividades de gamificação.


---

## Objetivos

Os principais objetivos deste diagrama são:
- **Definir o Escopo do Sistema:** Apresentar de forma clara e concisa todas as funcionalidades planejadas e implementadas.
- **Identificar os Atores:** Distinguir os diferentes tipos de usuários e suas respectivas permissões e interações.
- **Comunicar a Visão do Produto:** Servir como um documento central para alinhar a equipe de desenvolvimento, stakeholders e gerentes de projeto sobre o comportamento esperado do sistema.
- **Facilitar o Planejamento:** O uso de marcadores de status (`<<Done>>`, `<<Planned>>`) ajuda a visualizar o progresso do desenvolvimento e a priorizar as próximas funcionalidades a serem implementadas.
- **Base para Outros Diagramas:** Servir como ponto de partida para a criação de diagramas mais detalhados, como diagramas de sequência, atividade e estados, que exploram o fluxo interno de cada caso de uso.

---

## Diagrama

O diagrama a seguir representa a estrutura funcional do sistema "AprendendoComIA".

[Diagrama de Caso de Uso do Sistema AprendendoComIA](../assets/Diagrama%20de%20Sequência.png)

---

### Atores

Foram identificados dois atores principais que interagem com o sistema:

1.  **Visitante:** Representa um usuário não autenticado. Suas interações são limitadas a funções de descoberta, como visualizar a demonstração do produto, entender seu funcionamento e criar uma nova conta.
2.  **Usuário (Aluno):** Representa um usuário autenticado. Este ator herda todas as capacidades do "Visitante" (por meio de uma relação de **generalização**) e possui acesso a todas as funcionalidades centrais do aplicativo, como interagir com o tutor de IA, gerenciar seu vocabulário, participar de lições e jogos, e configurar seu perfil.

### 3.2. Organização em Pacotes

Para melhorar a clareza e a organização, as funcionalidades foram agrupadas em pacotes temáticos:

- **Onboarding:** Casos de uso relacionados ao primeiro contato do usuário, como login, cadastro e visualização de demonstração.
- **Chat com Tutor IA:** Funcionalidade central do sistema, onde o aluno pode praticar conversação, escrita e pronúncia com a assistência da IA.
- **Gamificação:** Engloba elementos que visam aumentar o engajamento, como sistema de níveis, ranking e desafios.
- **Mini-jogos:** Atividades lúdicas, como o "Desafio de Spelling", que complementam o aprendizado.
- **Vocabulário (SRS):** Sistema de Repetição Espaçada para ajudar o aluno a memorizar novas palavras.
- **Lições:** Módulos de aprendizado estruturados.
- **Perfil do Usuário:** Gerenciamento de dados pessoais, configurações e estatísticas de progresso.

---

### Legenda de Status

- **`<<Done>>`:** Indica um caso de uso que já foi implementado.
- **`<<Planned>>`:** Indica um caso de uso que está no escopo do projeto, mas ainda não foi desenvolvido.

---

## Bibliografia

- [Duolingo – Wikipedia](https://en.wikipedia.org/wiki/Duolingo)  
- [Babbel – Site Oficial](https://www.babbel.com/)  
- [ELSA Speak – Site Oficial](https://elsaspeak.com/en/)  
- [Language in India – Comparative Study](https://www.languageinindia.com/oct2024/drsunandauseAIEnglishlearning1.pdf)  
- [Sciedupress – Teaching with Apps](https://www.sciedupress.com/journal/index.php/jct/article/download/25589/16050)  
- [Arxiv – Gamification Misuse](https://arxiv.org/abs/2203.16175)  
- [SWEBOK – IEEE](https://www.computer.org/education/bodies-of-knowledge/software-engineering)  
- [LGPD – Gov.br](https://www.gov.br/cidadania/pt-br/acesso-a-informacao/lgpd)  
- [Sommerville – Engenharia de Software](https://www.pearson.com/en-us/subject-catalog/p/software-engineering/P200000003546/9780137035151)  
- [Miro – Arquitetura G3](https://miro.com/)  
- [Google Forms – Público Alvo](https://forms.gle/cB4qXso3j3tm2LVh6)

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data de Produção | Revisor(es) | Data de Revisão | Incremento do Revisor |
| :----: | --------- | --------- | :--------------: | ----------- | :-------------: | :-------------------: |
| `1.0`  | Modelagem inicial | [Felipe das Neves](https://github.com/FelipeFreire-gf) | 12/09/2025 |  | |  |
| `1.1` | Preenchimento das seções de técnica e objetivos | [Emivalto Da Costa](https://github.com/EmivaltoJrr) | 21/09/2025 | | | | 

