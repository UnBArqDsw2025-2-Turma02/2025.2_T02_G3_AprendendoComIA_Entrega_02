# Diagrama de Classes

---
## Sumário
- [Propósito do artefato](#propósito-do-artefato)
- [Como ler o diagrama (guia rápido)](#como-ler-o-diagrama-guia-rápido)
- [Versão 1 (draw.io) — visão ampla inicial](#versão-1-drawio--visão-ampla-inicial)
- [Versão 2 (PlantUML) — visão por camadas](#versão-2-plantuml--visão-por-camadas)
- [Destaques do Domínio](#destaques-do-domínio)
- [Fluxo entre camadas (Front → API → Services → Repo → Domínio)](#fluxo-entre-camadas-front--api--services--repo--domínio)
- [Comparativo V1 × V2](#comparativo-v1--v2)
- [Legenda (símbolos e notações UML)](#legenda-símbolos-e-notações-uml)
- [Bibliografia](#bibliografia)
- [Histórico de Versões](#histórico-de-versões)

---

## Propósito do artefato
O **Diagrama de Classes** sintetiza a estrutura estática do sistema **AprendendoComIA**: *quais classes existem, quais atributos e operações possuem, e como se relacionam*.  
Este artefato cumpre três objetivos:

1. **Mapear o Domínio de Negócio**: usuários, tarefas, sessões de chat, correções, SRS (flashcards e revisões), gamificação (objetivos, progresso, ranking), dicionário/idiomas, grupos e reações.
2. **Evidenciar a Arquitetura em Camadas**: *Frontend* → *API (Next.js routes)* → *Services* → *Repositories* → *Domínio* → *Infra*.  
3. **Apoiar decisões de projeto**: multiplicidades, encapsulamento (`+`/`-`/`#`), dependências e fronteiras entre módulos.

---

## Como ler o diagrama (guia rápido)
- **Classes** são caixas com *atributos* (tipo à direita) e *métodos* (assinatura). Ex.:  
  `User { +email: string  +name: string  +cefLevel: string  +lastStudyDate: Date }`
- **Modificadores**: `+` público, `-` privado, `#` protegido.
- **Associações** usam **multiplicidades** (ex.: `"1" -- "0..*"`) e **papéis** (ex.: `writes`, `receives`).
- **Herança**: `A <|-- B` (B herda de A).  
- **Composição / Agregação**: `*--` (vida controlada) / `o--` (vida independente).
- **Dependências** (entre camadas) são setas **tracejadas** `..>`.

---

## Versão 1 (draw.io) — visão ampla inicial
> Arquivo: **Diagrama de Classes.drawio.png**

![Versão 1 — draw.io](https://github.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/blob/ab90e55f210327e9563f59dfa7a73e275974b300/docs/assets/Diagrama%20de%20Classes.drawio.png?raw=true)

<font size="2"><p style="text-align: center">Fonte: [Arthur Carvalho](https://github.com/arthurlleite),  2025.</p></font>

**Intenção:** consolidar *todo o universo* do sistema (domínio + arquitetura) em uma única visão.  
**Vantagens**
- Cobertura extensa: Chat, Tarefas, SRS, Gamificação, Dicionário/Idioms, Grupos/Interações, Visão/Upload, etc.
- Multiplicidades e papéis já especificados.

**Limitações**
- **Poluição visual (“macarrão”)**: muitas ligações cruzando áreas distintas.
- Mistura de níveis (domínio + camadas técnicas) no mesmo plano → aumenta a carga cognitiva.
- Dificulta manutenção e incrementos.

---

## Versão 2 (PlantUML) — visão por camadas
> Arquivo: **Diagrama de Classespt2.png**

![Versão 2 — PlantUML](https://github.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/blob/main/docs/assets/Diagrama%20de%20Classespt2.png?raw=true)

<font size="2"><p style="text-align: center">Fonte: [Arthur Carvalho](https://github.com/arthurlleite),  2025.</p></font>

**Intenção:** reorganizar a mesma informação por **pacotes**, tornando legível o fluxo entre camadas e a responsabilidade de cada módulo.

### Pacotes e elementos principais
- **Domain**:  
  `User`, `Task`, `WritingTask`, `LetterTask`, `Submission`, `LetterSubmission`,  
  `ChatSession`, `ChatTurn`, `Correction`,  
  `SRSCard`, `SRSReview`,  
  `DictionaryEntry`, `IdiomEntry`,  
  `TutorPersona`,  
  `Group`, `Reaction`,  
  `Goal`, `GoalProgress`, `LeaderboardEntry`,  
  `VisualContext`,  
  `ListeningQuiz`, `ListeningQuestion`,  
  `SpellingBeeTask`, `SpellingAttempt`.

- **Services** (*regras de negócio orquestradas*):  
  `AuthService`, `ChatService`, `TaskService`, `SRSService`,  
  `DictionaryService`, `GamificationService`, `ListeningService`, `SpellingService`,  
  `PersonaService`, `VisionService`, `SocialService`.

- **API (Next.js Routes)** (*adaptadores HTTP*):  
  `AuthRoutes`, `ChatRoutes`, `TaskRoutes`, `SRSRoutes`, `DictionaryRoutes`,  
  `GamificationRoutes`, `ListeningRoutes`, `SpellingRoutes`,  
  `PersonaRoutes`, `VisionRoutes`, `SocialRoutes`, `TutorRoutes`.

- **Repositories** (*acesso a dados / persistência*):  
  `UserRepository`, `TaskRepository`, `ChatRepository`, `SRSRepository`,  
  `DictionaryRepository`, `GamificationRepository`, `PersonaRepository`, `MediaRepository`.

- **Front** (*páginas/feature modules*):  
  `LandingPage`, `DashboardPage`, `TaskPage`, `ChatPage`, `GamificationPage`,  
  `SpellingBeePage`, `ListeningQuizPage`, `DictionaryPanel`,  
  `PersonaPicker`, `SocialRoomPage`, `CameraContextPage`, `DemoPage`.

- **Infra** (*infraestrutura de execução e cross cutting*):  
  `AppMiddleware` (rotas privadas/públicas e CORS), `EnvPrivate`, `EnvPublic`,  
  `NextApp`, `MongoDB`, `Nginx`, `PublicAssets`.

**Benefícios da V2**
- Leitura clara do pipeline **Front → API → Services → Repositories → Domain**.
- Multiplicidades legíveis, sem sobreposição.
- Facilita onboarding e revisão técnica; cada pacote pode ser lido isoladamente.

---

## Destaques do Domínio
- **Aprendizagem**:  
  `Task` (abstrata) tem especializações: `WritingTask` (texto livre) e `LetterTask` (modelo + rubrica).  
  `Submission`/`LetterSubmission` registram respostas e **scores**.  
  `SRSCard`/`SRSReview` suportam *spaced repetition*.

- **Chat com IA**:  
  `ChatSession` (dono é `User`) agrega `ChatTurn` (mensagens) e `Correction` (apontamentos grammar/style).

- **Gamificação**:  
  `Goal`/`GoalProgress`, `LeaderboardEntry` (XP, minutos, streak), `Reaction` (interações sociais).

- **Vocabulário**:  
  `DictionaryEntry` e `IdiomEntry` (definições, exemplos) para *lookup* e *context help*.

- **Listening / Spelling**:  
  `ListeningQuiz` contém `ListeningQuestion`.  
  `SpellingBeeTask` agrupa `SpellingAttempt`.

- **Social**:  
  `Group` (aberto/fechado, `members:number`) e `Reaction` (emojis e meta social).

---

## Fluxo entre camadas (Front → API → Services → Repo → Domínio)
1. **Front** invoca um *endpoint* em **API** (e.g., `POST /api/tasks/submit`).
2. **API** valida/normaliza o input e chama o **Service** correspondente (e.g., `TaskService.submit()`).
3. **Service** aplica *regras de negócio*; consulta/atualiza o **Domínio** via **Repositories**.
4. **Repositories** persistem entidades em **MongoDB** (mapeadas pelas classes de *domínio*).
5. **Service** retorna DTO/Result → **API** transforma em HTTP Response → **Front** atualiza a UI.

> Setas **tracejadas** no diagrama evidenciam essas dependências; as **associações** (linhas sólidas) ficam no *Domínio*.

---

## Comparativo V1 × V2

| Critério | Versão 1 (draw.io) | Versão 2 (PlantUML) |
|---|---|---|
| Organização | Monolítica, tudo junto | Em **pacotes** (camadas) |
| Legibilidade | Linhas se cruzam (macarrão) | Fluxo **claro** e setas organizadas |
| Evolução | Ajustes caros | Incrementos locais por pacote |
| Auditoria | Ampla mas poluída | Ampla **e** legível |
| Uso | Foto “geralzona” do sistema | Base viva para documentação e revisão |

---

## Legenda (símbolos e notações UML)

| Símbolo / Notação | Significado |
|---|---|
| `class Nome { +pub()  -priv : Tipo  #prot }` | Classe com **métodos/atributos**; `+` público, `-` privado, `#` protegido. |
| `A "1" -- "0..*" B : role` | **Associação** com **multiplicidade** e **papel** (texto após `:`). |
| `A <|-- B` | **Herança/Generalização**: `B` herda de `A`. |
| `A *-- B` | **Composição**: `B` só existe acoplado ao ciclo de vida de `A`. |
| `A o-- B` | **Agregação**: `A` referencia `B`, mas `B` tem vida própria. |
| `A ..> B` | **Dependência** (usa/chama/consulta). Usada para *acoplamento entre camadas*. |
| `package "Nome"` | Agrupamento lógico (ex.: *Domain*, *Services*, *API*, *Repositories*, *Front*, *Infra*). |
| `<<stereotype>>` | Marca semântica (ex.: `<<Routes>>`, `<<Service>>`). |
| `1`, `0..1`, `0..*`, `1..*` | Cardinalidades: um; opcional; muitos; um ou muitos. |

**Recomendação de leitura:** comece pelo *Domain* (entidades centrais), depois percorra `Front → API → Services → Repositories → Domain`, acompanhando as setas tracejadas.

---

## Bibliografia
- [OMG — Unified Modeling Language (UML) Specification](https://www.omg.org/spec/UML/)  
- [Martin Fowler — UML Distilled](https://martinfowler.com/books/uml.html)  
- [IEEE — SWEBOK (Software Engineering Body of Knowledge)](https://www.computer.org/education/bodies-of-knowledge/software-engineering)  
- [PlantUML — Class & Package Diagrams](https://plantuml.com/class-diagram)  
- [Domain-Driven Design — Eric Evans (overview)](https://www.domainlanguage.com/ddd/)  
- [Next.js — App Router & Route Handlers](https://nextjs.org/docs/app/building-your-application/routing/route-handlers)  
- [MongoDB — Data Modeling](https://www.mongodb.com/docs/manual/core/data-modeling-introduction/)

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data de Produção | Revisor(es) | Data de Revisão |
| :----: | --------- | --------- | :--------------: | ----------- | :-------------: |
| `1.0`  | Versão inicial (draw.io) com visão ampla | [arthurlleite](https://github.com/arthurlleite) | 21/09/2025 |  |  |
| `1.1`  | Reorganização por pacotes (PlantUML) e revisão de multiplicidades | [arthurlleite](https://github.com/arthurlleite) | 21/09/2025 |  |  |
| `1.2`  | Documento explicativo unificado (este arquivo) com guia de leitura e legenda | [arthurlleite](https://github.com/arthurlleite) | 21/09/2025 |  |  |