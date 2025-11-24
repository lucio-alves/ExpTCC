# 1. Identificação Básica

## 1.1 Título do Experimento
**A Crise de Meia-Idade dos Softwares: Análise de Sobrevivência e Pontos de Abandono em Repositórios Pessoais**

## 1.2 ID / Código
**EXP-2024-MSR-PILOTO-01**

## 1.3 Versão do Documento e Histórico de Revisão
| Versão | Data       | Autor      | Descrição das Alterações                 |
|--------|------------|------------|-------------------------------------------|
| v1.0   | 21/11/2025 | Lúcio Alves| Elaboração inicial do plano de experimento |

## 1.4 Datas (criação, última atualização)
- **Criação:** 21/11/2025 
- **Última atualização:** 21/11/2025 

## 1.5 Autores 
- **Autor:** Lúcio Alves 
- **Área:** Engenharia de Software / Pesquisa Acadêmica  
- **Contato:** *lucioalvesalmeidaneto@gmail.com*

## 1.6 Responsável Principal (PI / Dono do Experimento)
**Lúcio Alves** (Pesquisador Principal)

## 1.7 Projeto / Produto / Iniciativa Relacionada
Este experimento atua como **Projeto Piloto (MVP)** para a iniciativa de TCC intitulada *"Impacto do Truck Factor na Descontinuidade de Software"*.  
O objetivo é validar a infraestrutura de coleta de dados e métricas de longevidade antes de aplicá-las no estudo principal.

---

# 2. Contexto e Problema

## 2.1 Descrição do Problema / Oportunidade
Existe uma lacuna de dados sobre o ciclo de vida de projetos pessoais open source.  
Embora seja conhecido que o abandono é frequente, não há clareza sobre um possível padrão temporal, um "período crítico", onde a desistência ocorre com maior intensidade.

A oportunidade é mapear a **curva de desistência**, para entender quanto tempo dura a motivação inicial de um desenvolvedor, validando a hipótese de que a maioria dos projetos morre dentro de uma janela específica (ex.: **3 a 6 meses**).

## 2.2 Contexto Organizacional e Técnico
- **Tipo de Organização:** Ambiente Acadêmico de Pesquisa  
- **Domínio:** Repositórios públicos do GitHub, focando em linguagens populares entre iniciantes (Python / JavaScript)

### Tecnologias e Ferramentas
- **Linguagem de Script:** Python 3  
- **Coleta de Dados:** GitHub REST API, PyGithub  
- **Processamento:** Pandas (manipulação de dados)  
- **Visualização:** Matplotlib / Seaborn  
- **Ambiente de Execução:** Google Colab

## 2.3 Trabalhos e Evidências Prévias (Internos e Externos)
### Internos
- Não há experimentos prévios realizados pelo autor sobre o tema.

### Externos
- Relatórios anuais **GitHub State of the Octoverse**, que mostram volume de criação, mas não taxas detalhadas de mortalidade.  
- Estudos acadêmicos sobre *Abandonware* e sustentabilidade de software OSS.  
- Evidências anedóticas da comunidade (“Hobby Projects”) sugerindo alta mortalidade nas primeiras semanas.

## 2.4 Referencial Teórico e Empírico Essencial
- **Mineração de Repositórios de Software (MSR):** Utiliza dados históricos de versionamento para analisar comportamento de desenvolvimento.  
- **Análise de Sobrevivência:** Estatística aplicada para medir tempo até um evento de “falha” — aqui, o abandono do repositório.  
- **Time-to-Abandonment:** Métrica definida como o intervalo entre o primeiro e o último commit.  
- **Hipótese da Curva da Empolgação:** Teoria que sugere que o esforço em projetos pessoais decai rapidamente após o fim da novidade inicial.

# 3. Objetivos e questões (Goal / Question / Metric)

## 3.1 Objetivo geral (Goal template)

### Elemento

-   **Analisar**
    -   Repositórios de software pessoais (Open Source)
-   **Com o propósito de**
    -   Caracterizar a longevidade, identificar pontos críticos de
        abandono e validar infraestrutura de coleta de dados
-   **Sob a perspectiva de**
    -   Pesquisador de Engenharia de Software (MSR)
-   **No contexto de**
    -   Projetos criados no GitHub durante o ano de 2022, nas linguagens
        Python e JavaScript

## 3.2 Objetivos específicos

-   **O1:** Mapear a distribuição estatística do tempo de vida
    (Lifespan) dos repositórios para determinar a mediana de
    sobrevivência.
-   **O2:** Investigar a existência de um padrão de "morte precoce"
    (abandono nos primeiros meses) e quantificar esse fenômeno.
-   **O3:** Analisar se a escolha da linguagem de programação (Python
    vs. JavaScript) influencia a taxa de abandono.
-   **O4:** Correlacionar o tamanho e complexidade inicial do projeto
    com sua capacidade de sobrevivência a longo prazo.

## 3.3 e 3.4 Matriz GQM (Questões e Métricas)

### O1 (Distribuição)

-   **Q1.1** Qual é a mediana e a média de tempo de vida dos projetos
    analisados?
    -   **Métricas:**
        -   M01 --- Lifespan (Days)
        -   M02 --- Date Created
-   **Q1.2** Qual a proporção de projetos "One-Hit Wonder" (apenas um
    dia de atividade)?
    -   **Métricas:**
        -   M03 --- Commit Count
        -   M01 --- Lifespan (Days)
-   **Q1.3** Existe uma variação significativa na longevidade entre
    semestres de criação?
    -   **Métricas:**
        -   M02 --- Date Created
        -   M01 --- Lifespan (Days)

### O2 (Morte Precoce)

-   **Q2.1** Qual a porcentagem de repositórios abandonados em menos de
    90 dias?
    -   **Métricas:**
        -   M04 --- Early Dropout Rate
        -   M01 --- Lifespan (Days)
-   **Q2.2** Em qual mês ocorre o pico de taxa de abandono?
    -   **Métricas:**
        -   M05 --- Peak Abandonment Month
        -   M06 --- Last Commit Date
-   **Q2.3** Projetos que sobrevivem aos primeiros 3 meses tendem a
    durar quanto tempo mais?
    -   **Métricas:**
        -   M07 --- Conditional Lifespan
        -   M01 --- Lifespan (Days)

### O3 (Linguagem)

-   **Q3.1** Existe diferença estatística na mediana de vida entre
    projetos Python e JavaScript?
    -   **Métricas:**
        -   M08 --- Primary Language
        -   M01 --- Lifespan (Days)
-   **Q3.2** Qual linguagem apresenta maior taxa de projetos com menos
    de 10 commits?
    -   **Métricas:**
        -   M08 --- Primary Language
        -   M03 --- Commit Count
-   **Q3.3** A frequência de commits varia conforme a linguagem?
    -   **Métricas:**
        -   M09 --- Commit Frequency
        -   M08 --- Primary Language

### O4 (Complexidade)

-   **Q4.1** Projetos que iniciam maiores (em KB) tendem a viver mais?
    -   **Métricas:**
        -   M10 --- Repository Size
        -   M01 --- Lifespan (Days)
-   **Q4.2** A quantidade de arquivos iniciais é um preditor de
    longevidade?
    -   **Métricas:**
        -   M11 --- File Count (Initial)
        -   M01 --- Lifespan (Days)
-   **Q4.3** Repositórios com descrições detalhadas sobrevivem mais?
    -   **Métricas:**
        -   M12 --- Description Length
        -   M01 --- Lifespan (Days)

# 4. Escopo e contexto do experimento

## 4.1 Escopo funcional / de processo

### Incluído

-   Repositórios públicos criados entre 01/01/2022 e 31/12/2022.
-   Linguagens: Python e JavaScript.
-   Projetos pessoais (usuário normal, não organização).
-   Análise de metadados e histórico de commits.

### Excluído

-   Repositórios Fork.
-   Repositórios com 0 ou 1 commit.
-   Análise qualitativa de código.
-   Análise de issues, PRs ou interações sociais.

## 4.2 Contexto do estudo

-   Pesquisa exploratória em contexto acadêmico.
-   Organização: Universidade / Trabalho Individual.
-   Tipo: Mineração de Dados e Análise Estatística.
-   Criticidade: Baixa.
-   Perfil: Projeto de aprendizado e validação técnica para TCC.

## 4.3 Premissas

-   A API do GitHub permanecerá estável.
-   Datas de commits representam corretamente o trabalho realizado.
-   Inatividade \> 12 meses representa abandono.

## 4.4 Restrições

-   Rate Limit: 5.000 requisições/hora.
-   Conclusão do experimento em 1 semestre.
-   Dados devem caber em memória local.

## 4.5 Limitações previstas

-   Resultados de Python/JS não representam outras linguagens.
-   Projetos "concluídos" podem parecer abandonados.
-   Commits automáticos podem distorcer padrões.

# 5. Stakeholders e impacto esperado

## 5.1 Stakeholders principais

-   Pesquisador (Aluno)
-   Orientador Acadêmico
-   Comunidade de MSR

## 5.2 Interesses e expectativas

-   Pesquisador: validar scripts e aprender técnicas de sobrevivência.
-   Orientador: garantir rigor metodológico.
-   Comunidade: acesso a dados empíricos sobre saúde do OSS.

## 5.3 Impactos

-   Processo: reduz risco técnico do TCC.
-   Produto: fornece base para capítulo analítico da monografia.

# 6. Riscos, premissas e critérios de sucesso

## 6.1 Riscos

-   Bloqueio por abuso da API.
-   Amostra majoritariamente de projetos inúteis/ruins.
-   ETL demorado demais.

## 6.2 Critérios de sucesso (go/no-go)

-   GO: coletar \> 1000 repositórios válidos.
-   GO: gerar CSV limpo e completo.
-   NO-GO: mudança nas permissões da API.

## 6.3 Critérios de parada antecipada

-   Mais de 90% dos dados serem bots/espelhos.
-   Revogação da chave da API.

# 7. Modelo conceitual e hipóteses

## 7.1 Modelo conceitual

-   **Entrada:** tamanho inicial, complexidade, linguagem.
-   **Processo:** fluxo de commits ao longo do tempo.
-   **Saída:** abandono.
-   **Esquema:** entusiasmo → dificuldades → queda de commits → morte.

## 7.2 Hipóteses

-   **H0:** taxa de abandono constante.
-   **H1:** abandono concentra-se nos primeiros 6 meses.
-   **H0_lang:** não há diferença entre Python e JS.
-   **H1_lang:** Python vive mais que JS.

## 7.3 Nível de significância

-   α = 0.05
-   Poder esperado \> 0.80




