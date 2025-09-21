# AprendendoComIA

**Código da Disciplina**: FGA0208<br>
**Número do Grupo**: 03<br>
**Entrega**: 02<br>

## Alunos

| Foto | Matrícula | Nome |
|------|-----------|------|
| <img src="https://avatars.githubusercontent.com/u/170873899?v=4" height="70"> | 22/2037595 | [Arthur Carvalho Leite](https://github.com/arthurlleite) |
| <img src="https://avatars.githubusercontent.com/u/138714054?v=4" height="70"> | 18/0100271 | [Emivalto Da Costa Tavares Junior](https://github.com/EmivaltoJrr) |
| <img src="https://avatars.githubusercontent.com/u/62055315?v=4" height="70"> | 20/2046102 | [Felipe das Neves Freire](https://github.com/FelipeFreire-gf) |
| <img src="https://avatars.githubusercontent.com/u/116119327?v=4" height="70"> | 22/2037610 | [Gabriel Lima](https://github.com/gabriel-lima258) |
| <img src="https://avatars.githubusercontent.com/u/105813929?v=4" height="70"> | 22/2037700 | [Leonardo de Melo Lima](https://github.com/leozinlima) |
| <img src="https://avatars.githubusercontent.com/u/99836497?v=4" height="70"> | 22/2022144 | [Luiz Henrique Soares ](https://github.com/luizh-gsoares) |
| <img src="https://avatars.githubusercontent.com/u/152661076?v=4" height="70"> | 23/102685 |[Letícia Monteiro ](https://github.com/leticiamonteiroo) |
| <img src="https://avatars.githubusercontent.com/u/164573233?v=4" height="70"> | 21/1062240 |[Mateus Bastos](https://github.com/MateuSansete) |
| <img src="https://avatars.githubusercontent.com/u/52254091?v=4" height="70"> | 21/2005444 | [Pedro Fonseca Cruz](https://github.com/pfc15) |
| <img src="https://avatars.githubusercontent.com/u/106821260?v=4" height="70"> | 21/1062473 | [Samuel Afonso da Silva Santos](https://github.com/SamuelAfonso) |
| <img src="https://avatars.githubusercontent.com/u/118318004?v=4" height="70"> | 18/0132466 | [Vitor Bessa](https://github.com/Bessazs) |

## Sobre

O aprendizado de inglês é uma das habilidades mais valorizadas globalmente, tanto no contexto acadêmico quanto profissional. De acordo com o relatório da [EF English Proficiency Index (2023)](https://www.ef.com.br/epi/), o Brasil ocupa a 58ª posição entre 113 países avaliados, sendo classificado com **nível baixo de proficiência**. Esse dado reforça a necessidade de soluções inovadoras que promovam maior engajamento e eficácia no processo de aprendizagem.  

Nos últimos anos, o uso de **Inteligência Artificial na educação (AI in Education)** tem ganhado destaque. Relatórios como o da [UNESCO (2022)](https://unesdoc.unesco.org/ark:/48223/pf0000376709) ressaltam que a IA pode personalizar o ritmo de aprendizado, identificar dificuldades específicas e oferecer feedback imediato, ampliando as oportunidades de acesso à educação de qualidade.  

Além disso, estudos sobre **gamificação aplicada ao ensino** mostram que estratégias baseadas em recompensas, rankings e desafios aumentam a motivação e a retenção de conhecimento. Segundo [Deterding et al. (2011)](https://dl.acm.org/doi/10.1145/2181037.2181040), a gamificação transforma atividades tradicionais em experiências mais atrativas e imersivas, com impacto positivo no engajamento dos estudantes.  

Diversos aplicativos já exploram esse potencial. O [Duolingo](https://www.duolingo.com/press), por exemplo, popularizou o aprendizado de idiomas com forte uso de gamificação, alcançando mais de 500 milhões de usuários. O [ELSA Speak](https://elsaspeak.com/), por outro lado, foca no aperfeiçoamento da pronúncia com tecnologia de reconhecimento de voz e feedback personalizado. Apesar disso, ainda há uma lacuna na integração entre **conteúdo estruturado, gamificação e prática de conversação em tempo real**.  

Nesse contexto, o projeto **Aprendendo com IA** busca preencher essa lacuna, oferecendo uma plataforma que combina **gamificação**, **conteúdo adaptativo** e um **tutor de conversação inteligente**, tornando o aprendizado de inglês mais **personalizado, acessível e motivador**.

## Screenshots da Segunda Entrega

### Diagrama de Componentes

![componentes](https://raw.githubusercontent.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/refs/heads/main/docs/modelagemEstatica/assets/componentes.png)

<center> Autor(a): <a href="https://github.com/leozinlima" target = "_blank">Gabriel Lima</a>, <a href="https://github.com/FelipeFreire-gf" target = "_blank">Felipe das Neves</a> e <a href="https://github.com/FelipeFreire-gf" target = "_blank">Mateus Bastos</a></center>

### Diagrama de Atividades

![atividades](https://raw.githubusercontent.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/refs/heads/main/docs/modelagemDinamica/assets/geral.png)
<center> Autor(a):  <a href="https://github.com/leozinlima" target = "_blank">Gabriel Lima</a> e <a href="https://github.com/FelipeFreire-gf" target = "_blank">Felipe das Neves</a></center>

### Diagrama de Pacotes

![atividades](https://raw.githubusercontent.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_Entrega_02/refs/heads/main/docs/ModelagemOrganizacional/assets/pacotes.png)
<center> Autor(a): <a href="https://github.com/leozinlima" target = "_blank">Gabriel Lima</a> e <a href="https://github.com/FelipeFreire-gf" target = "_blank">Felipe das Neves</a> </center>


## Há algo a ser executado?

(x) SIM

( ) NÃO

Obs.: O projeto está no mesmo repositório: https://github.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_DEV

### Opção 1: Acesso Rápido via Docker do nosso Software
```bash
# Baixar e rodar o projeto
unzip ai-linguo.zip && cd ai-linguo
cp .env.example .env
docker-compose up --build

# Acessar: http://localhost:3000
```

### Opção 2: Repositório GitHub
```bash
# Clonar o repositório
git clone https://github.com/UnBArqDsw2025-2-Turma02/2025.2_T02_G3_AprendendoComIA_DEV
cd ai-linguo

# Configurar e rodar
cp .env.example .env
yarn install
docker-compose up mongo -d
yarn seed
yarn dev
```

## Informações Complementares 

Para executar a documentação em ambiente local siga os seguintes passos:

### Instale o docsify

Execute o comando:

```shell
npm i docsify-cli -g
```

### Executando localmente

Para iniciar o site localmente, utilize o comando::

```shell
docsify serve ./docs
```



