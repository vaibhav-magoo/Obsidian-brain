
# Paradigms of AI systems
 - Single LLM
![[Pasted image 20260317105116.png]]
 
 
 - Structured workflows ![[Pasted image 20260317105139.png]]
 
 - Autonomous agents ![[Pasted image 20260317105203.png]]

|AI System type|Process|Use Case|Pros|Cons|
|---|---|---|---|---|
|**Single LLM**|Input → LLM → Output|Summarization, classification|Simple, fast, low cost|Not adaptable, lacks context|
|**Workflow**|Parallel LLMs → Aggregation → Output|Structured multi-step tasks|Predictable, easy to audit|Rigid, not dynamic|
|**Agent**|Plan → Act → Observe → (repeat agent loop)|Complex, adaptive automation|Flexible, learns from feedback|Unpredictable, complex, pricier|




# When to use AI agents
| Type                       | Description                                                 | Best Use Cases                                       |
| -------------------------- | ----------------------------------------------------------- | ---------------------------------------------------- |
| **Simple AI Features**     | Perform tasks like classification or text summarization     | Fast, repeatable tasks with clear outputs            |
| **Orchestrated Workflows** | Predefined multi-step logic combining different AI features | Structured processes like document review or routing |
| **Autonomous Agents**      | Make decisions independently and adapt to new information   | Complex reasoning, exploration, or strategy tasks    |
### 4 criteria framework:
 - if task is ambiguous use AI agents
 - AI agents will consume 10-100 times more tokens than workflows
 - before launching test if the agents can meet 5 key skills of the required task
 - have room for mistakes and correction of the mistakes
### Key elements of agent architecture:
 - Environment(the digital space of operation)
 - Tools (the interfaces the agents use)
 - System Prompts
 
> Start simple with your agent's actions. Add task complexity only after confirming the agent's reliable performance.


# Tool calling

> [!NOTE]
> Tool calling is a technique that enables a large language model (LLM) to be aware of and interact with real-time data sources, such as databases or APIs. In this process, a client application sends a set of messages along with a tool definition to the LLM. 

#### embedded tool calling
 - Instead of sending messages directly to the LLM, you use a library or framework that acts as a middleman.
 - This library not only defines the tools you want to use but also executes the tool calls for you
 - helps ensure that the responses are accurate and relevant.