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

