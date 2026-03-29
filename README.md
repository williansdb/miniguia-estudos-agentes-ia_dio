# Miniguia de Estudos: Agentes de IA com NotebookLM 🤖

## 🎯 Contexto e Objetivos
Este repositório foi desenvolvido para o desafio de projeto da **DIO (Digital Innovation One)**. O foco do estudo é o ecossistema de **Agentes de IA**, explorando como modelos de linguagem (LLMs) podem ser transformados em sistemas autônomos capazes de planejar tarefas, utilizar ferramentas e interagir com ambientes externos.

O objetivo é consolidar o aprendizado sobre arquiteturas de agentes, utilizando o **NotebookLM** para sintetizar referências de alto nível técnico.

---

## 📚 Curadoria de Fontes
Para este estudo, foram selecionadas fontes que abrangem desde a teoria acadêmica até a implementação prática em frameworks modernos:

1.  **[LangChain Python Overview](https://docs.langchain.com/oss/python/langchain/overview)** - Documentação oficial do framework líder para orquestração de LLMs e agentes.
2.  **[Langflow: Agents & Tools](https://docs.langflow.org/agents)** - Guia sobre a construção visual de agentes e a integração de ferramentas dinâmicas.
3.  **[Lil'Log - LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)** - O artigo seminal de Lilian Weng que define os pilares de Planejamento, Memória e Uso de Ferramentas.
4.  **[AutoGen: Enabling Next-Gen LLM Applications](https://arxiv.org/abs/2308.08155)** - Paper científico sobre sistemas multi-agentes e conversas colaborativas entre IAs.
5.  **[NVIDIA Glossary: What are AI Agents?](https://www.nvidia.com/en-us/glossary/ai-agents/)** - Definição técnica e visão de mercado sobre o futuro da autonomia em IA pela NVIDIA.

---

## 🧠 Engenharia de Prompts e "Cicatrizes"
Documentação do processo de interação com o NotebookLM:

### Prompts Estratégicos:
* **Prompt de Definição:** "Com base no artigo da Lilian Weng, quais são os três componentes principais que transformam um LLM em um Agente?"
* **Prompt de Ferramentas (Langflow):** "Como o Langflow facilita a integração de 'Tools' para que um agente possa realizar ações fora de seu treinamento?"

### Troubleshooting (Cicatrizes):
* **Dificuldade:** Diferenciar a 'Memória de Curto Prazo' (Contexto do Prompt) da 'Memória de Longo Prazo' (RAG/Vetores).
* **Solução:** Foi necessário solicitar que a IA fizesse uma tabela comparativa entre os tipos de memória citados nas documentações do LangChain e Lil'Log para clarear os conceitos.

---

## 📖 Miniguia de Estudo (Entrega Final)

### Resumos Estruturados
Um Agente de IA moderno opera sob o ciclo **Raciocínio -> Ação -> Observação**. 
* **Autonomia:** Diferente de um chatbot, o agente decide *qual* ferramenta usar (ex: uma busca no Google ou rodar um código Python) para resolver um problema.
* **Multi-Agentes (AutoGen):** A capacidade de colocar dois ou mais agentes para "conversarem" e revisarem o trabalho um do outro, aumentando a precisão.

### Glossário de Conceitos
* **ReAct (Reason + Act):** Paradigma onde o modelo escreve seu pensamento antes de executar uma ação.
* **Tools (Ferramentas):** Interfaces (APIs) que permitem ao agente interagir com o mundo real.
* **Orquestração:** O processo de gerenciar o fluxo de informações entre o usuário e o agente (ex: o que o LangChain faz).

### Prompts Reutilizáveis
> "Explique o conceito de 'Tool Use' em Agentes de IA para um estudante de Segurança da Informação, dando um exemplo de como um agente poderia usar uma ferramenta de varredura de rede."

---
