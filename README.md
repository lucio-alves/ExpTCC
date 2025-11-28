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

# 8. Variáveis, fatores, tratamentos e objetos de estudo

## 8.1 Objetos de estudo
Os objetos de estudo são **repositórios de software hospedados publicamente no GitHub**. Especificamente, serão analisados os metadados do projeto (tamanho, linguagem, descrição) e o histórico de versionamento (log de commits, timestamps).

## 8.2 Sujeitos / participantes (visão geral)
Neste estudo de MSR (Mining Software Repositories), não há participantes humanos ativos realizando tarefas em tempo real. Os "sujeitos" são, indiretamente, os **desenvolvedores proprietários das contas pessoais** que criaram os repositórios em 2022. O comportamento deles é analisado *post-mortem* (após o fato) através dos rastros digitais deixados nos commits.

## 8.3 Variáveis independentes (fatores) e seus níveis
Os fatores que serão utilizados para segmentar e comparar os dados são:
* **Fator A: Linguagem de Programação Principal**
    * Nível 1: Python
    * Nível 2: JavaScript
* **Fator B: Complexidade Inicial (Tamanho)**
    * Nível 1: Pequeno (definido pelo 1º quartil da amostra)
    * Nível 2: Médio/Grande (acima do 1º quartil)

## 8.4 Tratamentos (condições experimentais)
Como se trata de um estudo observacional (ex-post facto) e não de um experimento controlado manipulado, os "tratamentos" referem-se aos grupos naturais observados:
1.  **Grupo Python:** Repositórios onde a linguagem dominante detectada pelo GitHub é Python.
2.  **Grupo JavaScript:** Repositórios onde a linguagem dominante detectada pelo GitHub é JavaScript.
*A distinção ocorre pela tecnologia escolhida pelo desenvolvedor no momento da criação.*

## 8.5 Variáveis dependentes (respostas)
As medidas de resultado (retomando a seção 3) são:
1.  **Lifespan (Tempo de Vida):** Dias entre o primeiro e o último commit (`LastDate - CreateDate`).
2.  **Status de Sobrevivência:** Variável binária indicando se o projeto sobreviveu além de um limiar temporal (ex: > 90 dias).
3.  **Densidade de Manutenção:** Frequência de commits durante o período de vida.

## 8.6 Variáveis de controle / bloqueio
Fatores mantidos constantes para reduzir ruído:
* **Período de Criação:** Apenas projetos criados em 2022 (para garantir janela de observação igual).
* **Tipo de Proprietário:** Apenas contas de usuários (`User`), excluindo organizações (`Organization`).
* **Origem:** Apenas repositórios originais, excluindo `Forks`.

## 8.7 Possíveis variáveis de confusão conhecidas
* **Bots e Automação:** Commits gerados automaticamente podem inflar o tempo de vida. (Mitigação: filtro de autores conhecidos como bots).
* **Repositórios de "Curso/Aula":** Projetos feitos apenas para acompanhar uma aula e abandonados propositalmente.
* **Sazonalidade:** Projetos iniciados em férias escolares podem ter padrões diferentes de projetos iniciados em época letiva.

---

# 9. Desenho experimental

## 9.1 Tipo de desenho
Será utilizado um **Estudo de Coorte Retrospectivo (Longitudinal)**.
*Justificativa:* Não é possível randomizar desenvolvedores para usar Python ou JS. Devemos olhar para trás (retrospectivo) em uma coorte (grupo) de projetos iniciados em 2022 e observar como eles evoluíram ao longo do tempo.

## 9.2 Randomização e alocação
Não haverá randomização de sujeitos. A alocação nos grupos (Python vs. JS) é determinada pela propriedade intrínseca do repositório.
Para a seleção dos dados, se o universo de dados exceder o limite da API, será feita uma **amostragem aleatória simples** dentro do conjunto de resultados retornados pela query de busca do GitHub.

## 9.3 Balanceamento e contrabalanço
* **Balanceamento:** O script de coleta buscará garantir que o tamanho da amostra final seja equiparável para ambos os grupos (ex: 1000 repositórios Python e 1000 JavaScript), descartando excedentes do grupo majoritário se necessário.
* **Contrabalanço:** Não aplicável, pois não há ordem de tarefas executadas por humanos.

## 9.4 Número de grupos e sessões
* **Grupos:** 2 Grupos principais (Python e JavaScript).
* **Sessões:** 1 Sessão única de extração de dados. O script roda uma vez para coletar todo o histórico disponível até a data presente.

---

# 10. População, sujeitos e amostragem

## 10.1 População-alvo
A população alvo são desenvolvedores de software (estudantes, hobbistas e profissionais) que utilizam o GitHub para hospedar projetos pessoais de código aberto.

## 10.2 Critérios de inclusão de sujeitos (Repositórios)
Para ser elegível, o repositório deve:
1.  Ter sido criado entre 01/01/2022 e 31/12/2022.
2.  Ter a linguagem primária identificada como Python ou JavaScript.
3.  Ser público.
4.  Possuir ao menos 2 commits (para permitir cálculo de intervalo de tempo).

## 10.3 Critérios de exclusão de sujeitos
Serão descartados:
1.  Repositórios marcados como `Fork`.
2.  Repositórios sem descrição ou vazios.
3.  Projetos identificados como "trabalho de casa" óbvio (ex: nomes como "TP1-Algoritmos" ou "Lista-Exercicios"), caso o volume seja alto e distorça a análise de "projetos pessoais".

## 10.4 Tamanho da amostra planejado
* **Total:** 2.000 a 4.000 repositórios.
* **Por Grupo:** Mínimo de 1.000 repositórios válidos para Python e 1.000 para JavaScript.
* *Justificativa:* Amostras grandes são necessárias em MSR devido à alta variância e ruído nos dados (muitos projetos abandonados no dia 1).

## 10.5 Método de seleção / recrutamento
Seleção via **GitHub Search API**.
A query será construída para buscar repositórios criados nas datas estipuladas. A seleção dos IDs será feita aleatoriamente a partir das páginas de resultados da API para evitar viés de relevância (já que o GitHub ordena por "best match" por padrão).

## 10.6 Treinamento e preparação
Não aplicável a participantes humanos.
A "preparação" refere-se à validação dos scripts de coleta (ver seção 11.4 - Piloto).

---

# 11. Instrumentação e protocolo operacional

## 11.1 Instrumentos de coleta
1.  **Scripts Python:** Código customizado utilizando a biblioteca `PyGithub` para interagir com a API.
2.  **GitHub REST API v3:** Fonte primária dos dados brutos.
3.  **Notebook Google Colab:** Ambiente onde os scripts serão executados e os dados tabulados.

## 11.2 Materiais de suporte
* Documentação oficial da API do GitHub.
* Lista de Tokens de Acesso Pessoal (PAT) para evitar bloqueio por *Rate Limit*.

## 11.3 Procedimento experimental (Protocolo)
1.  **Configuração:** Carregar chaves de API e bibliotecas no ambiente Python.
2.  **Descoberta:** Executar query de busca para listar URLs de repositórios candidatos (meta: 5.000 candidatos).
3.  **Filtragem Prévia:** Iterar sobre a lista e descartar Forks ou projetos arquivados/bloqueados.
4.  **Extração Profunda:** Para cada repositório válido:
    * Baixar metadados (stars, size, description).
    * Baixar lista de commits (datas, autores).
5.  **Cálculo de Métricas:** Calcular `Lifespan` e outras métricas derivadas localmente.
6.  **Persistência:** Salvar dados em arquivo CSV (`dataset_raw.csv`).
7.  **Limpeza:** Remover outliers extremos e dados inconsistentes.

## 11.4 Plano de piloto
* **Escopo:** Execução completa do pipeline com apenas 50 repositórios de cada linguagem.
* **Objetivo:** Verificar se as métricas de tempo estão sendo calculadas corretamente e estimar o tempo de execução (custo de API) para a amostra total.
* **Ajuste:** Se o tempo de coleta for > 1 hora, otimizar chamadas de API (ex: usar GraphQL em vez de REST).

---

# 12. Plano de análise de dados (pré-execução)

## 12.1 Estratégia geral de análise
A análise será focada em **Análise de Sobrevivência**. Os dados serão tratados como tempo até a ocorrência de um evento (o "abandono").

## 12.2 Métodos estatísticos planejados
1.  **Estimador Kaplan-Meier:** Para plotar as curvas de sobrevivência de ambos os grupos e visualizar a queda de participação ao longo do tempo.
2.  **Teste Log-Rank:** Para testar a hipótese nula de que não há diferença na sobrevivência entre projetos Python e JavaScript (comparação das curvas).
3.  **Estatística Descritiva:** Média, Mediana e Desvio Padrão para tempo de vida e número de commits.

## 12.3 Tratamento de dados faltantes e outliers
* **Faltantes:** Repositórios com dados corrompidos na API serão excluídos da amostra (listwise deletion).
* **Outliers:** Projetos com tempo de vida > 365 dias serão mantidos (pois são casos de sucesso), mas projetos com > 10.000 commits (provável bot/espelho) serão removidos para não distorcer a média.

## 12.4 Plano de análise para dados qualitativos
Não haverá análise qualitativa profunda (leitura de código). A análise será estritamente quantitativa baseada em metadados.

---

# 13. Avaliação de validade (ameaças e mitigação)

## 13.1 Validade de conclusão
* *Ameaça:* Poder estatístico insuficiente devido a alta variância.
* *Mitigação:* Uso de amostra grande (> 2000 itens) para garantir robustez nos testes estatísticos.

## 13.2 Validade interna
* *Ameaça (Maturação/História):* O "abandono" pode ser apenas uma migração para outro host (GitLab) ou mudança de nome do repositório.
* *Mitigação:* Assumir a premissa de que, para fins de análise do GitHub, a inatividade > 1 ano equivale a abandono na plataforma. Não é possível rastrear o dev fora do GitHub.

## 13.3 Validade de constructo
* *Ameaça:* A métrica "Last Commit Date" pode não refletir o abandono real (ex: o dev parou meses antes e deu um push final de limpeza).
* *Mitigação:* Considerar a densidade de commits. Se houver um gap muito grande antes do último commit, considerar a data anterior.

## 13.4 Validade externa
* *Ameaça:* Os resultados de 2022 podem não se aplicar a 2025 ou a linguagens corporativas (Java/C#).
* *Mitigação:* Deixar claro no relatório que o escopo é limitado a linguagens de script dinâmicas em contexto de projetos pessoais recentes.

## 13.5 Resumo das principais ameaças
| Ameaça | Estratégia |
| :--- | :--- |
| Projetos de "Brinquedo" (Hello World) | Filtrar repos com < 2 commits ou < 3 arquivos. |
| Limitação da API (Amostragem enviesada) | Randomizar a paginação da busca. |
| Identificação incorreta de linguagem | Confiar na classificação majoritária do GitHub (Linguist). |

---

# 14. Ética, privacidade e conformidade

## 14.1 Questões éticas
O estudo utiliza dados secundários públicos. Não há interação direta com seres humanos nem intervenção no ambiente de trabalho deles. O risco ético é mínimo ("Minimal Risk").

## 14.2 Consentimento informado
Ao utilizar o GitHub, os usuários concordam com os Termos de Serviço que permitem a visualização pública de seus repositórios. A coleta de dados para fins acadêmicos (sem fins comerciais ou de identificação maliciosa) está dentro do uso aceitável da plataforma. Não é necessário consentimento explícito individual.

## 14.3 Privacidade e proteção de dados
* **Dados Coletados:** Nome do repositório, nome do usuário (login), datas, mensagens de commit.
* **Proteção:** No dataset final divulgado (se houver), os nomes de usuários e e-mails serão **pseudoanonimizados** (substituídos por hash ID) para evitar indexação por motores de busca e preservar a privacidade dos desenvolvedores amadores.
* **Retenção:** Dados brutos com identificadores serão apagados após a defesa do TCC.

## 14.4 Aprovações necessárias
* **Comitê de Ética:** Geralmente dispensado para dados públicos de MSR, mas será consultado o orientador para confirmação das regras da instituição.
* **Plataforma:** O uso deve respeitar o *Rate Limit* e os *Terms of Service* do GitHub.

---

# 15. Recursos, infraestrutura e orçamento

## 15.1 Recursos humanos e papéis
* **Pesquisador (Lúcio Alves):** Desenvolvimento dos scripts, coleta, análise estatística e escrita.
* **Orientador:** Revisão do desenho experimental e validação dos resultados.

## 15.2 Infraestrutura técnica necessária
* **Computador Pessoal:** Para desenvolvimento e processamento leve.
* **Google Colab (Free Tier):** Para execução dos scripts de coleta (vantagem de IP rotativo e ambiente nuvem).
* **Armazenamento:** Google Drive (aprox. 500MB de espaço para CSVs).

## 15.3 Materiais e insumos
* Conta no GitHub (para geração de Token).
* Bibliotecas Python: `PyGithub`, `pandas`, `lifelines` (para análise de sobrevivência), `matplotlib`.

## 15.4 Orçamento e custos estimados
O projeto é de **baixo custo financeiro**, dependendo principalmente de horas-homem.

| Item | Custo Estimado (R$) | Fonte |
| :--- | :--- | :--- |
| Licença GitHub API | R$ 0,00 (Gratuito) | Free Tier |
| Google Colab | R$ 0,00 (Gratuito) | Free Tier |
| Horas de Trabalho (Pesquisador) | 100h (Inestimável) | Dedicação Acadêmica |
| **Total Financeiro** | **R$ 0,00** | - |


