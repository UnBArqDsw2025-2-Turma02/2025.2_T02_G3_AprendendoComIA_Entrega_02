# Diagrama de Sequência

---

## Sumário
- [Visão e Propósito](#visão-e-propósito)
- [Imagem do Diagrama](#imagem-do-diagrama)
- [Escopo e Critérios](#escopo-e-critérios)
- [Fluxos Representados](#fluxos-representados)
- [Legenda de Símbolos](#legenda-de-símbolos)
- [Rótulos de Status](#rótulos-de-status)
- [Público x Privado](#público-x-privado)
- [Observações Arquiteturais](#observações-arquiteturais)
- [Histórico de Versões](#histórico-de-versões)

---

## Visão e Propósito
O diagrama de sequência consolida, em uma linha do tempo única, as interações centrais do produto: **autenticação**, **navegação de áreas públicas e privadas**, **tarefas com correção**, **chat com tutor IA** e **gamificação**. A intenção é oferecer uma leitura operacional do sistema, alinhada às histórias de usuário, sem detalhamento de implementação.

---

## Imagem do Diagrama
> Renderização consolidada do fluxo ponta a ponta (cliente, rotas Next.js, API interna, serviços e persistência).

![Diagrama de Sequência](https://raw.githubusercontent.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/main/docs/assets/Diagrama%20de%20Sequ%C3%AAncia.png)

<font size="2"><p style="text-align: center">Fonte: [Arthur Carvalho](https://github.com/arthurlleite),  2025.</p></font>

---

## Escopo e Critérios
- **Cobertura**: rotas **/landing** e **/demo** (públicas), áreas **/dashboard**, **/tasks**, **/chat** e **/gamification** (privadas), além das rotas **/api/** correspondentes.
- **Contrato**: uso de **JWT** via `auth_token (HttpOnly, SameSite=Lax)` para acesso às rotas privadas.
- **Persistência**: operações em **MongoDB** para usuários, tarefas, sessões e progresso.
- **Assíncrono**: marcações quando há chamadas que podem ser paralelas (ex.: registro de XP e eventos de gamificação).

---

## Fluxos Representados
1. **Acesso público**  
   Carregamento de **/landing** e **/demo**, sem dependência de sessão.

2. **Autenticação (login/registro)**  
   Envio das credenciais para **/api/auth/**, emissão do **JWT** e estabelecimento do cookie. Em sucesso, redirecionamento para área privada (padrão: **/dashboard**).

3. **Tarefas e Correção**  
   - Criação/listagem de tarefas via **/api/vocabulary/** e **/api/tutor/** (quando aplicável).  
   - Envio de respostas, retorno de correções, atualização de progresso e XP.

4. **Chat com Tutor IA**  
   - Abertura de sessão, envio de mensagens, recepção de respostas e correções embutidas (quando solicitado).  
   - Persistência do histórico e metadados da sessão.

5. **Gamificação**  
   - Leitura e atualização de ranking, XP e metas.  
   - Interação com grupos/competições (inscrição/entrada) e registro de conquistas.

---

## Legenda de Símbolos

### Participantes
| Elemento | Significado | Exemplos no diagrama |
|---|---|---|
| **Actor** | Entidade externa que interage com o sistema | Estudante / Visitante |
| **Boundary** | Interface de interação (UI/rota HTTP) | Páginas Next.js, `route.ts` de API |
| **Control** | Orquestra lógica de aplicação | `AuthService`, `TasksService` |
| **Entity** | Estruturas de dados/persistência | `users`, `tasks`, `sessions` |
| **Database** | Armazenamento | MongoDB |

### Mensagens
| Notação | Interpretação |
|---|---|
| **Seta sólida** `A -> B : ação()` | Chamada síncrona (A aguarda B) |
| **Seta tracejada** `A --> B : evento` | Sinal/retorno/ack |
| **Barra de ativação** | Janela de processamento do participante |
| **Fragmentos** `alt / opt / loop / par` | Condicional, opcional, repetição, paralelo |

### HTTP (resumo de uso)
| Método | Uso típico |
|---|---|
| `GET` | Leitura (páginas, listagens) |
| `POST` | Autenticação, criação e ações com payload |
| `PUT/PATCH` | Atualizações |
| `DELETE` | Remoções |
| `200/201/204` | Sucesso |
| `400/401/403/404/409/422` | Erros de requisição/autorização/estado |
| `500/503` | Falhas de serviço |

---

## Rótulos de Status
| Rótulo | Significado |
|---|---|
| **Done** | Implementado e validado |
| **In Progress** | Em desenvolvimento |
| **Planned** | Planejado |
| **Blocked** | Impedido por dependência |

> Os rótulos aparecem ao lado de trechos/lifelines para deixar claro o estágio de cada parte do fluxo.

---

## Público x Privado
| Escopo | Regra |
|---|---|
| **Público** | **/landing**, **/demo** e assets. Sem exigência de sessão. |
| **Privado** | **/dashboard**, **/tasks**, **/chat**, **/gamification** e **/api/** correlatas. Requer `auth_token` válido. Em ausência/erro, há **redirecionamento** para **/landing?from=...**. |

---

## Observações Arquiteturais
- **Next.js (App Router)** concentra UI e rotas **/api/**; o middleware aplica políticas de **CORS** e **autorização**.  
- **MongoDB** centraliza usuários, sessões de chat, tarefas, métricas de gamificação e progresso.  
- **Assíncrono** previsto para correções mais pesadas e eventos de gamificação (quando necessário).
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
- [Plantuml- Diagrama de Sequência](https://www.plantuml.com/)

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data de Produção | Revisor(es) | Data de Revisão |
| :----: | --------- | --------- | :--------------: | ----------- | :-------------: |
| `1.0`  | Primeira versão consolidada do diagrama e legenda | [Arthur Carvalho](https://github.com/arthurlleite) | 21/09/2025 | — | — |