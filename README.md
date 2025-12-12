# 1. Identificação Básica

## 1.1 Título do Experimento
**A Vida dos Repositórios de Software: Análise de Sobrevivência e Pontos de Abandono em Repositórios Pessoais**

## 1.2 ID / Código
**EXP-2024-MSR-PILOTO-01**

## 1.3 Versão do Documento e Histórico de Revisão
| Versão | Data       | Autor      | Descrição das Alterações                 |
|--------|------------|------------|-------------------------------------------|
| v1.3   | 28/11/2025 | Lúcio Alves| Elaboração inicial do plano de experimento |

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
Este experimento atua como **Projeto Piloto (MVP)** para a iniciativa de TCC intitulada *"SECRET"*.  
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

# 3. Objetivos e Questões (Goal / Question / Metric)

## 3.1 Objetivo Geral (Goal Template)

| Elemento | Descrição |
| :--- | :--- |
| **Analisar** | Repositórios de software pessoais (Open Source) |
| **Com o propósito de** | Caracterizar a longevidade, identificar pontos críticos de abandono e validar infraestrutura de coleta |
| **Sob a perspectiva de** | Pesquisador de Engenharia de Software (MSR) |
| **No contexto de** | Projetos criados no GitHub durante o ano de 2022, nas linguagens Python e JavaScript |

## 3.2 Objetivos Específicos

-   **O1:** Mapear a distribuição estatística do tempo de vida (Lifespan) dos repositórios para determinar a mediana de sobrevivência.
-   **O2:** Investigar a existência de um padrão de "morte precoce" (abandono nos primeiros meses) e quantificar esse fenômeno.
-   **O3:** Analisar se a escolha da linguagem de programação (Python vs. JavaScript) influencia a taxa de abandono.
-   **O4:** Correlacionar o tamanho e complexidade inicial do projeto com sua capacidade de sobrevivência a longo prazo.

## 3.3 e 3.4 Matriz GQM (Questões e Métricas)

### O1 (Distribuição)
| ID Questão | Pergunta (Question) | Métricas Associadas (Metric) |
| :--- | :--- | :--- |
| **Q1.1** | Qual é a mediana e a média de tempo de vida dos projetos analisados? | **M01** - Lifespan (Days)<br>**M02** - Date Created |
| **Q1.2** | Qual a proporção de projetos "One-Hit Wonder" (apenas um dia de atividade)? | **M03** - Commit Count<br>**M01** - Lifespan (Days) |
| **Q1.3** | Existe uma variação significativa na longevidade entre semestres de criação? | **M02** - Date Created<br>**M01** - Lifespan (Days) |

### O2 (Morte Precoce)
| ID Questão | Pergunta (Question) | Métricas Associadas (Metric) |
| :--- | :--- | :--- |
| **Q2.1** | Qual a porcentagem de repositórios abandonados em menos de 90 dias? | **M04** - Early Dropout Rate<br>**M01** - Lifespan (Days) |
| **Q2.2** | Em qual mês ocorre o pico de taxa de abandono? | **M05** - Peak Abandonment Month<br>**M06** - Last Commit Date |
| **Q2.3** | Projetos que sobrevivem aos primeiros 3 meses tendem a durar quanto tempo mais? | **M07** - Conditional Lifespan<br>**M01** - Lifespan (Days) |

### O3 (Linguagem)
| ID Questão | Pergunta (Question) | Métricas Associadas (Metric) |
| :--- | :--- | :--- |
| **Q3.1** | Existe diferença estatística na mediana de vida entre projetos Python e JavaScript? | **M08** - Primary Language<br>**M01** - Lifespan (Days) |
| **Q3.2** | Qual linguagem apresenta maior taxa de projetos com menos de 10 commits? | **M08** - Primary Language<br>**M03** - Commit Count |
| **Q3.3** | A frequência de commits varia conforme a linguagem? | **M09** - Commit Frequency<br>**M08** - Primary Language |

### O4 (Complexidade)
| ID Questão | Pergunta (Question) | Métricas Associadas (Metric) |
| :--- | :--- | :--- |
| **Q4.1** | Projetos que iniciam maiores (em KB) tendem a viver mais? | **M10** - Repository Size<br>**M01** - Lifespan (Days) |
| **Q4.2** | A quantidade de arquivos iniciais é um preditor de longevidade? | **M11** - File Count (Initial)<br>**M01** - Lifespan (Days) |
| **Q4.3** | Repositórios com descrições detalhadas sobrevivem mais? | **M12** - Description Length<br>**M01** - Lifespan (Days) |

## 3.5 Definição das Métricas
*Tabela de referência contendo descrição e unidade de todas as métricas citadas acima.*

| ID | Nome da Métrica | Descrição da Métrica | Unidade |
| :--- | :--- | :--- | :--- |
| **M01** | Lifespan | Diferença temporal entre o último e o primeiro commit do repositório. | Dias |
| **M02** | Date Created | Data de criação do repositório registrada no GitHub. | Data (YYYY-MM-DD) |
| **M03** | Commit Count | Número total de commits realizados no branch principal. | Inteiro (Contagem) |
| **M04** | Early Dropout Rate | Percentual de projetos da amostra com Lifespan < 90 dias. | Porcentagem (%) |
| **M05** | Peak Abandonment Month | O mês (relativo ao início do projeto) onde ocorre o maior número de últimos commits. | Inteiro (Mês ordinal) |
| **M06** | Last Commit Date | Data do último commit registrado no repositório. | Data (YYYY-MM-DD) |
| **M07** | Conditional Lifespan | Expectativa de vida adicional dado que o projeto já sobreviveu X dias. | Dias |
| **M08** | Primary Language | Linguagem predominante detectada pelo GitHub Linguist. | Categórica (Nominal) |
| **M09** | Commit Frequency | Média de commits por dia ativo. | Commits/Dia |
| **M10** | Repository Size | Tamanho do repositório em disco no momento da coleta. | Kilobytes (KB) |
| **M11** | File Count (Initial) | Número de arquivos presentes no primeiro commit/semana do projeto. | Inteiro (Contagem) |
| **M12** | Description Length | Número de caracteres na descrição (about) do repositório. | Inteiro (Caracteres) |

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
Neste estudo de MSR (*Mining Software Repositories*), não há participantes humanos ativos realizando tarefas em tempo real. Os "sujeitos" são, indiretamente, os **desenvolvedores proprietários das contas pessoais** que criaram os repositórios em 2022. O comportamento deles é analisado *post-mortem* através dos rastros digitais deixados nos commits.

## 8.3 Variáveis independentes (fatores) e seus níveis
Os fatores que serão utilizados para segmentar e comparar os dados são:
* **Fator A: Linguagem de Programação Principal**
    * Nível 1: Python
    * Nível 2: JavaScript
* **Fator B: Complexidade Inicial (Tamanho)**
    * Nível 1: Pequeno (definido pelo 1º quartil da amostra)
    * Nível 2: Médio/Grande (acima do 1º quartil)

## 8.4 Tratamentos (condições experimentais)
Como se trata de um estudo observacional e não de um experimento controlado manipulado, os "tratamentos" referem-se aos grupos naturais formados pelas escolhas dos desenvolvedores. A tabela abaixo ilustra o desenho fatorial e as combinações de tratamento:

| ID do Grupo | Fator A: Linguagem | Fator B: Complexidade (Tamanho)* | Descrição do Tratamento (Combinação) |
| :--- | :--- | :--- | :--- |
| **G1 (PY-S)** | Python | Pequeno (1º Quartil) | Projetos Python de baixa complexidade inicial. |
| **G2 (PY-L)** | Python | Médio/Grande (> 1º Quartil) | Projetos Python de maior complexidade inicial. |
| **G3 (JS-S)** | JavaScript | Pequeno (1º Quartil) | Projetos JavaScript de baixa complexidade inicial. |
| **G4 (JS-L)** | JavaScript | Médio/Grande (> 1º Quartil) | Projetos JavaScript de maior complexidade inicial. |
*\*Nota: A definição de "Pequeno" e "Grande" será baseada na distribuição estatística (quartis) dos dados coletados.*

## 8.5 Variáveis dependentes (respostas)
As medidas de resultado focam na longevidade e atividade:
1.  **Lifespan (Tempo de Vida):** Dias entre o primeiro e o último commit.
2.  **Status de Sobrevivência:** Variável binária (0 ou 1) indicando se o projeto sobreviveu além de um limiar temporal (ex: > 90 dias).
3.  **Densidade de Manutenção:** Frequência de commits durante o período de vida.

## 8.6 Variáveis de controle / bloqueio
Fatores mantidos constantes para reduzir ruído e garantir a comparabilidade da amostra. A tabela a seguir resume todas as variáveis do estudo (Independentes, Dependentes e de Controle):

### Tabela Resumo das Variáveis
| Tipo de Variável | Nome da Variável | Descrição Operacional | Escala / Unidade |
| :--- | :--- | :--- | :--- |
| **Independente (Fator)** | Linguagem Principal | A linguagem predominante no repositório detectada pelo GitHub. | Nominal (Python, JavaScript) |
| **Independente (Fator)** | Tamanho Inicial | O tamanho do repositório em KB no momento da coleta. | Ordinal (Pequeno, Médio/Grande) |
| **Dependente (Resposta)** | Lifespan (Tempo de Vida) | Diferença em dias entre a data do último commit e a data de criação. | Razão (Dias) |
| **Dependente (Resposta)** | Status de Sobrevivência | Indicador binário se o projeto ultrapassou 90 dias de vida. | Nominal (0 = Morreu, 1 = Sobreviveu) |
| **Dependente (Resposta)** | Densidade de Manutenção | Quantidade de commits dividida pelo tempo de vida. | Razão (Commits/Dia) |
| **Controle** | Ano de Criação | Filtro aplicado para selecionar apenas projetos de 2022. | Intervalar (Ano 2022) |
| **Controle** | Tipo de Proprietário | Filtro para excluir organizações e manter apenas usuários individuais. | Nominal (User) |
| **Controle** | Origem do Repositório | Filtro para excluir *Forks* e manter apenas originais. | Nominal (Source) |

## 8.7 Possíveis variáveis de confusão conhecidas
* **Bots e Automação:** Commits gerados automaticamente podem inflar o tempo de vida. (Mitigação: filtro de autores conhecidos como bots).
* **Repositórios de "Curso/Aula":** Projetos feitos apenas para acompanhar uma aula e abandonados propositalmente.
* **Sazonalidade:** Projetos iniciados em férias escolares podem ter padrões diferentes de projetos iniciados em época letiva.

---

# 9. Desenho experimental

## 9.1 Tipo de desenho
Será utilizado um **Estudo de Coorte Retrospectivo (Longitudinal)**.
*Justificativa:* Não é possível randomizar desenvolvedores para usar Python ou JS aleatoriamente em seus projetos pessoais. A abordagem correta é olhar para trás em um corte (grupo) de projetos iniciados em 2022 e observar como eles evoluíram ao longo do tempo até o abandono.

## 9.2 Randomização e alocação
Não haverá randomização de sujeitos (desenvolvedores). A alocação nos grupos (Python vs. JS) é determinada pela propriedade do repositório.
Para a seleção dos dados, se o universo de dados exceder o limite da API, será feita uma **amostragem aleatória simples** dentro do conjunto de resultados retornados pela query de busca do GitHub.

## 9.3 Balanceamento e contrabalanço
* **Balanceamento:** O script de coleta buscará garantir que o tamanho da amostra final seja equiparável para ambos os grupos (ex: 1000 repositórios Python e 1000 JavaScript), descartando excedentes do grupo majoritário se necessário.
* **Contrabalanço:** Não aplicável, pois não há ordem de tarefas executadas por humanos.

## 9.4 Número de grupos e sessões
* **Grupos:** 2 Grupos principais (Python e JavaScript), subdivididos por complexidade conforme Tabela 8.4.
* **Sessões:** 1 Sessão única de extração de dados. O script roda uma vez para coletar todo o histórico disponível até a data presente.

---

# 10. População, sujeitos e amostragem

## 10.1 População-alvo
A população alvo são desenvolvedores de software que utilizam o GitHub para hospedar projetos pessoais de código aberto.

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
3.  Projetos identificados como "trabalho de casa" óbvio (ex: nomes como "TP1-Algoritmos" ou "Lista-Exercicios"), caso o volume seja alto e distorça a análise de "projetos pessoais voluntários".

## 10.4 Tamanho da amostra planejado
* **Total:** 2.000 a 4.000 repositórios.
* **Por Grupo:** Mínimo de 1.000 repositórios válidos para Python e 1.000 para JavaScript.
* *Justificativa:* Amostras grandes são necessárias em MSR devido à alta variância e ruído nos dados (muitos projetos abandonados no dia 1, os chamados "one-hit wonders").

## 10.5 Método de seleção / recrutamento
Seleção via **GitHub Search API**.
A query será construída para buscar repositórios criados nas datas estipuladas. A seleção dos IDs será feita aleatoriamente a partir das páginas de resultados da API para evitar viés de relevância (visto que o GitHub ordena por "best match" ou "most stars" por padrão).

## 10.6 Treinamento e preparação dos sujeitos
Não aplicável a participantes humanos. A "preparação" refere-se à validação técnica dos scripts de coleta (ver seção 11.4 - Piloto).

---

# 11. Instrumentação e protocolo operacional

## 11.1 Instrumentos de coleta
1.  **Scripts Python:** Código customizado utilizando a biblioteca `PyGithub` para interagir com a API.
2.  **GitHub REST API v3:** Fonte primária dos dados brutos.
3.  **Notebook Google Colab:** Ambiente onde os scripts serão executados e os dados tabulados.

## 11.2 Materiais de suporte
* Documentação oficial da API do GitHub.
* Lista de Tokens de Acesso Pessoal (PAT) para evitar bloqueio por *Rate Limit*.

## 11.3 Procedimento experimental (Protocolo – visão passo a passo)
1.  **Configuração:** Carregar chaves de API e bibliotecas no ambiente Python.
2.  **Descoberta:** Executar query de busca para listar URLs de repositórios candidatos (meta: 5.000 candidatos).
3.  **Filtragem Prévia:** Iterar sobre a lista e descartar Forks ou projetos arquivados/bloqueados.
4.  **Extração Profunda:** Para cada repositório válido:
    * Baixar metadados (stars, size, description).
    * Baixar lista de commits (datas, autores).
5.  **Cálculo de Métricas:** Calcular `Lifespan` e outras métricas derivadas localmente.
6.  **Persistência:** Salvar dados em arquivo CSV (`dataset_raw.csv`).
7.  **Limpeza:** Remover outliers extremos e dados inconsistentes.

## 11.3.1 Procedimento experimental (Diagrama)
<img width="1914" height="3883" alt="Untitled diagram-2025-12-01-001149" src="https://github.com/user-attachments/assets/0d81ed47-aee1-45a1-a815-84bb76798f39" />

## 11.4 Plano de piloto
* **Escopo:** Execução completa do pipeline com apenas 50 repositórios de cada linguagem.
* **Objetivo:** Verificar se as métricas de tempo estão sendo calculadas corretamente e estimar o tempo de execução (custo de API) para a amostra total.
* **Ajuste:** Se o tempo de coleta for > 1 hora, otimizar chamadas de API (ex: usar GraphQL em vez de REST para buscar commits e metadados em uma única query).

---

# 12. Plano de análise de dados (pré-execução)

## 12.1 Estratégia geral de análise
A análise será focada em **Análise de Sobrevivência**. Os dados não serão tratados apenas como médias simples, mas como "tempo até a ocorrência de um evento" (o evento sendo o abandono do repositório).

## 12.2 Métodos estatísticos planejados
1.  **Estimador Kaplan-Meier:** Para plotar as curvas de sobrevivência de ambos os grupos e visualizar a queda de participação ao longo do tempo.
2.  **Teste Log-Rank:** Para testar a hipótese nula de que não há diferença na sobrevivência entre projetos Python e JavaScript (comparação das curvas).
3.  **Estatística Descritiva:** Média, Mediana e Desvio Padrão para tempo de vida e número de commits.

## 12.3 Tratamento de dados faltantes e outliers
* **Faltantes:** Repositórios com dados corrompidos na resposta da API serão excluídos da amostra (*listwise deletion*).
* **Outliers:** Projetos com tempo de vida > 365 dias serão mantidos (pois são casos de sucesso, ou "censurados à direita"), mas projetos com > 10.000 commits (provável bot/espelho) serão removidos para não distorcer a média de atividade humana.

## 12.4 Plano de análise para dados qualitativos
Não haverá análise qualitativa profunda (leitura de código). A análise será estritamente quantitativa baseada em metadados.

---

# 13. Avaliação de validade (ameaças e mitigação)

## 13.1 Validade de conclusão
* *Ameaça:* Poder estatístico insuficiente devido à alta variância natural dos dados de software (muitos projetos morrem, poucos vivem muito).
* *Mitigação:* Uso de amostra grande (> 2.000 itens) para garantir robustez nos testes estatísticos e reduzir o erro padrão.

## 13.2 Validade interna
* *Ameaça (Maturação/História):* O "abandono" pode ser apenas uma migração para outro host (ex: GitLab) ou mudança de nome do repositório, sem que o projeto tenha realmente morrido.
* *Mitigação:* Assumir a premissa de que, para fins de análise do ecossistema GitHub, a inatividade > 1 ano equivale a abandono na plataforma. Não é viável rastrear o desenvolvedor fora do GitHub.

## 13.3 Validade de constructo
* *Ameaça:* A métrica "Last Commit Date" pode não refletir o abandono real (ex: o dev parou meses antes e deu um push final de limpeza apenas para arrumar o *readme*).
* *Mitigação:* Considerar a densidade de commits. Se houver um gap muito grande (> 6 meses) antes do último commit, considerar a data anterior ao gap como o fim efetivo do desenvolvimento ativo.

## 13.4 Validade externa
* *Ameaça:* Os resultados de 2022 podem não se aplicar a 2025 ou a linguagens corporativas (Java/C#).
* *Mitigação:* Deixar claro no relatório que o escopo é limitado a linguagens de *script* dinâmicas em contexto de projetos pessoais recentes, não generalizando para software industrial.

## 13.5 Resumo das principais ameaças e estratégias de mitigação
| Ameaça | Estratégia de Mitigação |
| :--- | :--- |
| Projetos de "Brinquedo" (*Hello World*) | Filtrar repositórios com < 2 commits ou < 3 arquivos. |
| Limitação da API (Amostragem enviesada) | Randomizar a paginação da busca para não pegar apenas os mais populares. |
| Identificação incorreta de linguagem | Confiar na classificação majoritária do GitHub (*Linguist*), aceitando pequena margem de erro. |

---

# 14. Ética, privacidade e conformidade

## 14.1 Questões éticas (uso de sujeitos)
O estudo utiliza dados secundários públicos. Não há interação direta com seres humanos nem intervenção no ambiente de trabalho deles. O risco ético é considerado mínimo (*Minimal Risk*).

## 14.2 Consentimento informado
Ao utilizar o GitHub, os usuários concordam com os Termos de Serviço que permitem a visualização pública e a clonagem de seus repositórios públicos. A coleta de dados para fins acadêmicos (sem fins comerciais ou de identificação maliciosa) está dentro do uso aceitável da plataforma. Não é necessário consentimento explícito individual de cada desenvolvedor.

## 14.3 Privacidade e proteção de dados
* **Dados Coletados:** Nome do repositório, nome do usuário (login), datas, mensagens de commit.
* **Proteção:** No dataset final divulgado (se houver), os nomes de usuários e e-mails serão **pseudoanonimizados** (substituídos por um ID hash) para evitar indexação direta por motores de busca e preservar a privacidade dos desenvolvedores amadores.
* **Retenção:** Dados brutos com identificadores serão apagados após a defesa do TCC.

## 14.4 Aprovações necessárias
* **Comitê de Ética:** Geralmente dispensado para dados públicos de MSR, mas será consultado o orientador para confirmação das regras específicas da instituição de ensino.
* **Plataforma:** O uso deve respeitar rigorosamente o *Rate Limit* e os *Terms of Service* do GitHub para evitar banimento da conta do pesquisador.

---

# 15. Recursos, infraestrutura e orçamento

## 15.1 Recursos humanos e papéis
* **Pesquisador Principal (Lúcio Alves):** Desenvolvimento dos scripts de coleta, execução do experimento, análise estatística e escrita da monografia.
* **Orientador Acadêmico:** Revisão do desenho experimental, orientação metodológica e validação dos resultados obtidos.

## 15.2 Infraestrutura técnica necessária
* **Computador Pessoal:** Para desenvolvimento dos scripts e redação.
* **Google Colab (Plano Gratuito):** Para execução dos scripts de coleta em nuvem (vantagem de IP rotativo e ambiente Python pré-configurado).
* **Armazenamento:** Google Drive (aprox. 500MB de espaço para CSVs brutos e processados).

## 15.3 Materiais e insumos
* Conta no GitHub (para geração de Token de Acesso Pessoal).
* Bibliotecas Python Open Source: `PyGithub`, `pandas`, `lifelines` (para análise de sobrevivência), `matplotlib`/`seaborn`.

## 15.4 Orçamento e custos estimados
O projeto é de **baixo custo financeiro**, dependendo principalmente de horas de dedicação do pesquisador.

| Item | Custo Estimado (R$) | Fonte de Financiamento |
| :--- | :--- | :--- |
| Licença GitHub API | R$ 0,00 (Gratuito) | Free Tier (Limite de 5k req/h) |
| Google Colab | R$ 0,00 (Gratuito) | Free Tier |
| Horas de Trabalho (Pesquisador) | ~120h (Inestimável) | Dedicação Acadêmica (Não remunerada) |
| **Total Financeiro** | **R$ 0,00** | - |

# 16. Cronograma, marcos e riscos operacionais

## 16.1 Macrocronograma (até o início da execução)
Considerando o cenário atual (final de 2025), o cronograma visa aproveitar o período de férias para a coleta massiva de dados.

| Fase | Atividade Chave | Previsão de Início | Previsão de Fim |
| :--- | :--- | :--- | :--- |
| **Planejamento** | Finalização do desenho experimental e revisão do plano | 20/11/2025 | 05/12/2025 |
| **Instrumentação** | Codificação dos scripts de mineração e testes de API | 01/12/2025 | 10/12/2025 |
| **Piloto** | Execução controlada (n=100) e validação de consistência | 11/12/2025 | 14/12/2025 |
| **Execução** | Coleta de dados completa (n > 2.000) e tratamento | 15/12/2025 | 22/12/2025 |
| **Análise** | Aplicação de estatística (Kaplan-Meier) e escrita dos resultados | 05/01/2026 | 28/02/2026 |

## 16.2 Dependências entre atividades
A execução segue um fluxo linear com dependências bloqueantes (*Hard Dependencies*):
1.  **Aprovação do Plano → Instrumentação:** O script só será finalizado após definição das variáveis exatas.
2.  **Sucesso do Piloto → Execução Massiva:** A coleta total só inicia se o piloto não apresentar erros de *Rate Limit* ou dados nulos.
3.  **Dataset Congelado → Análise Estatística:** A análise de sobrevivência requer que o dataset esteja fechado e limpo.

## 16.3 Riscos operacionais e plano de contingência

| Risco | Probabilidade | Impacto | Plano de Contingência |
| :--- | :--- | :--- | :--- |
| **Bloqueio da API (Rate Limit)** | Média | Alto (Interrupção) | Implementar *sleep timers* agressivos no código e utilizar chaves (Tokens) rotativas se necessário. |
| **Qualidade Ruim dos Dados** | Alta | Médio (Viés) | Reforçar filtros de exclusão pré-coleta (descartar projetos "Hello World" ou sem descrição). |
| **Perda de Dados Locais** | Baixa | Altíssimo | Sincronização automática dos arquivos `.csv` gerados no Google Colab para o Google Drive a cada 100 iterações. |
| **Mudança na API do GitHub** | Baixa | Alto (Refatoração) | Acompanhar o *Developer Blog* do GitHub; se houver *breaking changes*, ajustar o script para nova versão. |

# 17. Governança do experimento

## 17.1 Papéis e responsabilidades formais
* **Pesquisador Principal (Lúcio Alves):** Responsável pelo desenvolvimento de scripts, coleta, limpeza de dados e escrita da monografia. Tem autoridade técnica sobre o tratamento dos dados.
* **Orientador Acadêmico:** Responsável pela validação do método científico e aceite final do TCC. Atua como consultor em dúvidas estatísticas.

## 17.2 Ritos de acompanhamento pré-execução
* **Checkpoints Quinzenais:** Reuniões (remotas ou presenciais) para mostrar progresso do código e parciais do texto.
* **Revisão do Piloto (Milestone):** Reunião específica após o dia 14/12 para analisar a planilha gerada no piloto e autorizar a coleta final.

## 17.3 Processo de controle de mudanças no plano
Caso seja necessário alterar o escopo (ex: remover JavaScript e focar só em Python), o processo será:
1.  **Registro:** Atualizar a seção "Histórico de Revisão" deste documento.
2.  **Comunicação:** E-mail formal para o orientador justificando a mudança técnica.
3.  **Aprovação:** Aceite do orientador antes de rodar a coleta nova.

# 18. Plano de documentação e reprodutibilidade

## 18.1 Repositórios e convenções de nomeação
* **Localização:** Todo o material será hospedado em repositório público no GitHub ao final do trabalho.
* **Convenção de Arquivos:**
    * Scripts: `src/01_data_collection.py`, `src/02_data_cleaning.py`
    * Dados: `data/raw/dataset_2022_full.csv`, `data/processed/survival_data.csv`
    * Notebooks: `notebooks/analysis_survival_curves.ipynb`

## 18.2 Templates e artefatos padrão
* **Log de Execução:** O script gerará um arquivo `run.log` registrando data, hora, número de repositórios processados e erros encontrados.
* **Dicionário de Dados:** Arquivo `data_dictionary.md` explicando o significado de cada coluna do CSV final.

## 18.3 Plano de empacotamento para replicação futura
Para garantir a reprodutibilidade científica (Replication Package):
1.  **Ambiente Virtual:** Inclusão de arquivo `requirements.txt` com versões exatas das bibliotecas (`pandas`, `lifelines`, `PyGithub`).
2.  **Sementes Aleatórias:** Uso de `random_seed = 42` (ou similar) em funções de amostragem para que a seleção dos repositórios possa ser replicada.
3.  **Instruções:** Arquivo `README.md` detalhado com passo a passo para gerar novos Tokens do GitHub e rodar o script.

# 19. Plano de comunicação

## 19.1 Públicos e mensagens-chave pré-execução
* **Orientador:** Comunicar prontidão técnica ("O script roda sem erros") e cronograma de feriados ("A coleta rodará automaticamente durante o recesso").
* **Instituição de Ensino:** Cumprir os prazos de entrega de pré-projetos e relatórios parciais via sistema acadêmico.

## 19.2 Canais e frequência de comunicação
* **E-mail:** Canal oficial para envio de versões do documento e datasets.
* **Reuniões de Orientação:** Frequência quinzenal na fase de planejamento; sob demanda na fase de execução.

## 19.3 Pontos de comunicação obrigatórios
* Conclusão do Plano Experimental (v1.0).
* Início da Coleta de Dados (Aviso de "Go").
* Finalização da Coleta e início da Análise.
* Qualquer incidente que comprometa o prazo final do TCC.

# 20. Critérios de prontidão para execução (Definition of Ready)

## 20.1 Checklist de prontidão (itens que devem estar completos)
A fase de execução (coleta massiva) só será iniciada quando:

- [ ] **Plano:** Documento de planejamento aprovado pelo orientador.
- [ ] **Token:** Chave de API do GitHub configurada e testada.
- [ ] **Script:** Código rodando sem erros de sintaxe no Google Colab.
- [ ] **Piloto:** Amostra de 50-100 repositórios coletada e validada manualmente (verificado se as datas fazem sentido).
- [ ] **Storage:** Google Drive conectado e com espaço disponível.

## 20.2 Aprovações finais para iniciar a operação
* **Autoridade:** Orientador Acadêmico.
* **Forma de Aprovação:** E-mail ou validação verbal durante reunião de checkpoint.
* **Critério:** "O dataset do piloto parece consistente e as métricas respondem às perguntas da pesquisa."
