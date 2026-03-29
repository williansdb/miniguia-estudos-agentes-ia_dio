# Miniguia de Estudos: Agentes de IA com NotebookLM 🤖

## 🎯 Contexto e Objetivos
Este repositório foi desenvolvido para o desafio de projeto da **DIO (Digital Innovation One)**. O foco do estudo é o ecossistema de **Agentes de IA**, explorando como modelos de linguagem (LLMs) podem ser transformados em sistemas autônomos capazes de planejar tarefas, utilizar ferramentas e interagir com ambientes externos.

O objetivo é consolidar o aprendizado sobre arquiteturas de agentes, utilizando o **NotebookLM** para sintetizar referências de alto nível técnico e documentar a transição de modelos reativos para agentes proativos.

---

## 📚 Curadoria de Fontes
Para este estudo, foram selecionadas fontes que abrangem desde a teoria acadêmica até a implementação prática em frameworks modernos:

1.  **[LangChain Python Overview](https://docs.langchain.com/oss/python/langchain/overview)** - Framework líder para orquestração de LLMs e agentes.
2.  **[Langflow: Agents & Tools](https://docs.langflow.org/agents)** - Guia sobre a construção visual de agentes e integração de ferramentas dinâmicas.
3.  **[Lil'Log - LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)** - Artigo seminal de Lilian Weng sobre os pilares de Planejamento, Memória e Tool Use.
4.  **[AutoGen: Enabling Next-Gen LLM Applications](https://arxiv.org/abs/2308.08155)** - Paper científico sobre sistemas multi-agentes e conversas colaborativas.
5.  **[NVIDIA Glossary: What are AI Agents?](https://www.nvidia.com/en-us/glossary/ai-agents/)** - Visão técnica e de mercado sobre a autonomia em IA.

---

## 🧠 Engenharia de Prompts e "Cicatrizes"
Documentação do processo de interação com o NotebookLM para extrair conhecimento profundo:

### Pergunta Estratégica:
**"Como os agentes de IA se diferenciam de um simples RAG ou de um script Regex em Python?"**

**Resultado do Insight:**
* **Diferença do RAG:** Enquanto o RAG é um fluxo de "pergunta e resposta" (recupera e gera), o Agente usa o RAG apenas como uma ferramenta. O agente decide autonomamente *quando* precisa buscar dados externos.
* **Diferença do Regex:** O Regex é determinístico e baseado em regras fixas. O Agente usa o LLM como "cérebro" para lidar com ambiguidades, podendo escrever e corrigir códigos Python dinamicamente para atingir um objetivo.

### Troubleshooting (Cicatrizes):
* **Dificuldade:** Compreender a autonomia de decisão. No início, parecia que qualquer script que usava IA era um agente.
* **Solução:** Identifiquei que a "cicatriz" de aprendizado está no loop de raciocínio. Um agente avalia a eficácia de sua própria ação e decide o próximo passo, enquanto um script comum apenas segue um roteiro pré-programado.

---

## 📖 Miniguia de Estudo (Entrega Final)

### Diferenciação Técnica
| Tecnologia | Funcionamento | Nível de Autonomia |
| :--- | :--- | :--- |
| **Regex (Python)** | Padrões estáticos e fixos | Nulo (Determinístico) |
| **RAG Simples** | Recuperação de dados + Geração | Baixo (Reativo) |
| **Agente de IA** | Raciocínio -> Ação -> Observação | Alto (Autônomo) |

### 🚀 Exemplo Prático de Agente em Python (LangChain)
Para demonstrar o conceito de **Tool Use**, este script exemplifica um agente que decide usar ferramentas externas:

```python
from langchain_openai import ChatOpenAI
from langchain.agents import load_tools, initialize_agent, AgentType

# 1. Configuração do Motor de Raciocínio
llm = ChatOpenAI(model="gpt-4", temperature=0)

# 2. Ferramentas que o Agente pode decidir usar
tools = load_tools(["serpapi", "llm-math"], llm=llm)

# 3. Inicialização do Agente com loop de raciocínio
agent = initialize_agent(
    tools, 
    llm, 
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, 
    verbose=True
)

# 4. O Agente planeja sozinho como responder
prompt = "Qual o preço atual do Bitcoin e quanto eu teria se comprasse 0.5 BTC?"
agent.run(prompt)
