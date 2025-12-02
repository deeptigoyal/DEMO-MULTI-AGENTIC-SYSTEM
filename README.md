# DEMO-MULTI-AGENTIC-SYSTEM

This system performs end-to-end market research by running multiple specialized AI agents in a fixed LangGraph workflow, generating competitor, customer, trend, and pricing insights, and producing a final executive report.

- Defines a shared market-research state to store outputs from each agent.

- Creates five specialized AI agents: competitor analysis, customer insights, market trends, pricing strategy, and report writing.

- Uses LangGraph to build a DAG workflow connecting these agents sequentially.

- Each agent receives the state, adds its analysis, updates logs, and appends key insights.

- A central class orchestrates LLM setup, workflow execution, and query handling.

- Generates a final executive-ready market research report by synthesizing all agent outputs.

- Provides demo, interactive mode, and saving functionality.

Note: The flow is strictly linear (Competitor → Customer → Trends → Pricing → Report) with no branching or decision-based routing. Each agent always runs next in the predefined DAG.


🚀 How Insights Are Generated in Code

The LLM is generating insight.

The agent (LangGraph) automatically:

- Takes input

- Decides which node should run next
(conditional routing)

- Executes a node

- Each node sends a prompt to the pretrained LLM

- The LLM gives output (insight)

- The agent stores output in state

- Moves to the next node

- Repeats until done

- So the actual “insight extraction” is happening inside each LLM call.

🧱 In short (very clear):

✔ The pretrained LLM produces the insights
✔ LangGraph agents control when and how many times the LLM is called
✔ The routing logic decides which insights to generate


✔ The pretrained LLM produces the insights
✔ LangGraph agents control when and how many times the LLM is called
✔ The routing logic decides which insights to generate
