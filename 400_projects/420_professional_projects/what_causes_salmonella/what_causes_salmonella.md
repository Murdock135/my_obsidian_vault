---
tags: project
status: ongoing
---
# Milestones
- [ ] #milestone Build the agentic system  #ongoing
- [ ] #milestone Generalize merging script
- [ ] #milestone Create the QA dataset #ongoing
- [x]  #milestone Build the planner #ongoing
- [ ] #milestone build the executor
- [ ] #milestone build the 
- [ ] #milestone build the aggregator
# Tasks

- [x] #task Parse the output from the llm #ongoing ✅ 2025-03-22
- [x] #task Use ChatPromptTemplate to format the message so that it is explicit as to what is the human message #planned ✅ 2025-03-29
- [x] #task Make powerpoint ✅ 2025-05-05
- [x] #task create a explorer ✅ 2025-05-08
- [x] #task get structured output ✅ 2025-04-24
- [x] #task add {df_heads} to the planner's system message #planned ✅ 2025-05-08
- [x] #task make the `pipeline` func with planner, executor #ongoing ✅ 2025-05-14
- [ ] #task migrate to langgraph #ongoing
	- [x] #task planner ✅ 2025-05-25
	- [ ] #task executor
- [ ] #task make the aggregator 
- [ ] #task the context info such as df_heads, tree should only be retrieved if router routes to planner. implement this #planned
- [x] #task create a router node that determines if the planner needs to be invoked or if it can answer the user's query itself. #ongoing ✅ 2025-05-25
- [ ] #task put test queries into config.toml #planned
- [ ] #task Add examples to the system message to implement few-shot.
- [ ] #task create a function to return a chatprompttemplate for an agent. Use kwargs to partially format.
- [ ] #task instead of invoking a new API call, add to the list of messages/ use memory. #planned
- [x] #task Extract the json plan #ongoing ✅ 2025-04-07
- [ ] #task Add a loop (max 5 times) to force proper output schema
- [ ] #task Integrate tools
	- [ ] #task e2b
	- [ ] #task filesystem
	- [ ] #task Human as a tool
	- [ ] #task openweathermap
	- [ ] #task oracleai vector search https://python.langchain.com/docs/integrations/tools/oracleai/
	- [ ] #task pubmed
	- [ ] #task python REPL
	- [ ] #task semantic scholar
	- [ ] #task wikipedia
- [ ] #task create a sandboxed environment with docker
- [x] #task Create a function in config.py that will create output directories stamped by time #ongoing ✅ 2025-05-05
- [x] #task move utility functions to utils.py #planned ✅ 2025-05-06
- [ ] #task Use Llama index for analysing the data and producing a json file that contains information on the datasets. 
- [ ] #task implement qa streaming https://js.langchain.com/docs/how_to/qa_streaming/
- [x] #task Fix the paths pointing to the data so that they are generic enough to be reproducible #planned(5m) ✅ 2025-03-21
- [x] #task use an if name == main #planned ✅ 2025-03-19
- [x] #task incorporate ollama with langchain ✅ 2025-03-21
	- [x] #task read langchain-ollama (30m) #ongoing ✅ 2025-03-21
- [x] #task put data used for research (proof of concept inside a separate dir) #planned ✅ 2025-03-20
- [x] #task Put the data documentations in a folder from which the llm can extract information. #ongoing ✅ 2025-03-20
- [ ] #task create a script to extract raw poultry sampling data
- [ ] #task Peruse the questions. For each question, write a sample reasoning flow.
- [ ] #task Write READMEs for the datasets on huggingface. #discuss
- [x] #task Read Python's 'Input and Output' tutorial #ongoing ✅ 2025-03-21
- [ ] #task Write a README.md on how to use data. Explain who to request access from, how to use the data and where to keep results in.
- [x] #task Create schematic of langchain system. ✅ 2025-05-14
- [x] #task Read about FAISS ✅ 2025-05-14
	- [x] #task Read the Github wiki ✅ 2025-05-14
	- [x] #task Read the Github README.md ✅ 2025-03-17
- [ ] #task Review and test repo 'salmonella_study'
	- [x] #task config.py ✅ 2025-03-17
	- [x] #task data_preprocessing.py ✅ 2025-03-17
	- [x] #task utils.py ✅ 2025-03-17
	- [x] #task setup.py ✅ 2025-03-17
	- [ ] #task scripts/preprocessing/merge_datasets.py
	- [ ] #task scripts/processing/expand_merged.py
- [ ] #task create list of important variables (written in notepad)

# Notes
## Remember the pillars/themes
- Data uniformization and merging.
- Exploratory Data Analysis.
- Agentic system for root-cause analysis.
- Missing data handling.
## Rambling
- Brainstorm how to handle comments within NORS
- Ramblings about time series
	- A smoothed time period e.g. a monthly progression would be better?
	- Model the temperature
	- Think about the occurence of salmonella as a process (Salmonella inception -> Salmonella observation)
- Is it possible to infer location of contamination?
- Can we get outputs in terms of probabilities?
- How can we impute missing data?
- Maybe we can use LllamaIndex/Llamaparse to
	- Clean and Merge datasets.
	- add the data documentations.
- Provide a list of URLs the LLM should scrape when trying to answer a question.
- Find all APIs for datasets.
- Need to discuss how to incorporate data on same thing e.g. poultry sampling, but for different time periods. For example 2013 will be different from 2014.
- Build a knowledge graph
	- Build a knowledge graph that links entities like county's economic profile with salmonella rates and encodes data like correlations, causal hypothesis.
	- Incorporate ontologies and domain-specific taxonomies to ensure that relationships are semantically meaningful and can be interpreted universally. (Recommendation by gpt o3 mini)
	- By fusing datasets into a semantic network, the system creates a unified representation that reveals hidden relationships. The knowledge graph paves the way for advanced querying (e.g., using SPARQL) and allows for richer insights through the exploitation of network structures and connectivity
- On providing info about data
	- Unless we use a bug model, we should do it manually because if we iterate over the datasets and provide df.head(), the datasets which are excel files would quickly consume the context window. 
- Using langgraph
	- We don't need to add messages to a node unless its the executor because the executor needs to use its own previous executions. 
	- A candidate structure for the state object
```python
	class State(TypedDict):
		query: str
		plan: Plan # create 'Plan' object before
		results: List[StateMessage]
```
- Add the system prompts and llms in the [runtime configuration](https://langchain-ai.github.io/langgraph/how-tos/graph-api/#add-runtime-configuration).
```python
from langchain.chat_models import init_chat_model
from langchain_core.runnables import RunnableConfig
from langgraph.graph import MessagesState
from langgraph.graph import END, StateGraph, START
from typing_extensions import TypedDict


class ConfigSchema(TypedDict):
    model: str


MODELS = {
    "anthropic": init_chat_model("anthropic:claude-3-5-haiku-latest"),
    "openai": init_chat_model("openai:gpt-4.1-mini"),
}


def call_model(state: MessagesState, config: RunnableConfig):
    model = config["configurable"].get("model", "anthropic")
    model = MODELS[model]
    response = model.invoke(state["messages"])
    return {"messages": [response]}


builder = StateGraph(MessagesState, config_schema=ConfigSchema)
builder.add_node("model", call_model)
builder.add_edge(START, "model")
builder.add_edge("model", END)

graph = builder.compile()

# Usage
input_message = {"role": "user", "content": "hi"}
# With no configuration, uses default (Anthropic)
response_1 = graph.invoke({"messages": [input_message]})["messages"][-1]
# Or, can set OpenAI
config = {"configurable": {"model": "openai"}}
response_2 = graph.invoke({"messages": [input_message]}, config=config)["messages"][-1]

print(response_1.response_metadata["model_name"])
print(response_2.response_metadata["model_name"])
```
- Parallelise certain computations e.g. retrieval from various sources.
	- https://youtu.be/l7lvoiCvcVU?si=TBzufVs9xmojL0Kx
- Store data context as separate vector stores, which the language models will access based on need.
# References
-   [Argonne Researchers Win Gordon Bell Special Prize for Using Language Models to Track Virus Variants - High-Performance Computing News Analysis | insideHPC](https://insidehpc.com/2022/12/argonne-researchers-win-gordon-bell-special-prize-for-using-language-models-to-track-virus-variants/)
-  [Argonne researchers win Gordon Bell Special Prize for adapting language models to track virus variants | Argonne National Laboratory](https://www.anl.gov/article/argonne-researchers-win-gordon-bell-special-prize-for-adapting-language-models-to-track-virus#:~:text=Scientists%20from%20the%20U.S.%20Department,identifying%20how%20a%20virus%20evolves.)
-  [GenSLMs: Genome-scale language models reveal SARS-CoV-2 evolutionary dynamics](https://www.biorxiv.org/content/10.1101/2022.10.10.511571v1.full.pdf)
-  [Protein Generation via Genome-scale Language Models with Bio-physical Scoring](https://dl.acm.org/doi/pdf/10.1145/3624062.3626087)
-  [2310.04607] A Comprehensive Performance Study of Large Language Models on Novel AI Accelerators](https://arxiv.org/abs/2310.04607)
-  [CSV | 🦜️🔗 LangChain](https://python.langchain.com/v0.1/docs/use_cases/sql/csv/#%EF%B8%8F-security-note-%EF%B8%8F)
-  [An integrated deep learning and stochastic optimization approach for resource management in team-based healthcare systems](https://pdf.sciencedirectassets.com/271506/1-s2.0-S0957417421X0019X/1-s2.0-S0957417421012781/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjECoaCXVzLWVhc3QtMSJIMEYCIQCx6X2aU47F%2BSVWklnSFhBY35EUrvGvIQqN%2BgWfBYPG8wIhAKUsDJVed6ETOI3Bd8w7Mx05sIsb5tbK22nFiWvlFchqKrsFCOL%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQBRoMMDU5MDAzNTQ2ODY1IgyUfby4f%2BS0wAw%2FzwYqjwX2LbNDra%2FuNZsQ%2FgOIAcjm7%2Fuf5cpMsWj422RpmRjZrMPQwMd8OEbyqN5n6HF16cfiRohxCzuPVK1dnFniB0AaYo4QqbvTIELB4GQWYIOblEu6dhZXzTsC1ixmo%2BJhi0ScgE7wQq3Kl%2F09SuKwvsQR9X27QM4%2BaGlDPNjeBSZnIUx6Lf9VhfBKZg1cnj3F10tpo8G7wm0OV0SDJwuiMlgyJNJdjUxk6uy%2B9oGX7U%2FaTUGDS%2F4ZGswjO9CnPfp38Oyxis7reqIrgcTS%2FR3h%2FbVQfoBCrLVaJVYloR9oZwS6WwDIrUYgRCQ3Ei%2FbvfuhiEdeflUqR9Nw%2FikP6G%2BgFOMmlwhDDN3oleRIqqmrzsk3P9NRUSkyVYpPZlXNTMPz2mOeMPXGRqVG0BUVBnojlYbXcGSJiAtwJAZ8x68J2UU5s6Ly0hWlfPzIG66RjQI5KG%2FIR44KJJSGMECj6lifQ44VRFBoAjqoKxcGbuDry1Z%2Bq9ugGj6cvpST%2FS8YQtftpr0G91f%2FxvPAQoQhkH99%2FG15ufGBXX8WOr4UzHE4oDo7U4%2FzdBwzNu5FgXXJrrp2g5vHE8%2FoLvjsJqzrTf7sg5MiqTkbEuWDgzeOwxjAuSUm4%2Few0TAPqUDID7WepNWm0SltCnyyin9pI6li9m4saP4YZfcGeK4lgMMaIaVdBqFsQJXf8me98H4JBpCmPTeY6VRun98u5qANOJn3ln2Vcoic2urC6GMJxSXz%2BasmUDOeFUVXj2RdFjSOaq6YYOHbQI8hShgO8aYmBaA00AwIYtHDnLW4gGfPPZ2yuTF6VSYGUsOHGekT3AZ9a9y%2F4ovix%2FJuDzRr2iaZ3U3dC8TzEhVPK9hmjBG6kWrrwe3WxXZUMKG087oGOrABk8BAMxfq63KSRkVpYJ8kygITSUGvM%2Fdt3xXxNa1hvYTWWLFTl74%2FGm5RKbJs3Wv6uVL26dHCik5Q%2FEy6i0BEqv6Q1EU1uMU8j88Cp6wrXtMOq8pIz9ezvYmzoddsT7%2BTrUM%2ByALxackQ%2Ff9Qyv9C8mEF1zKYySuLbghJsy6j8gNScJC7jFAcmV%2B8SbfghzDkvRJMH%2FWw4FG5uqnYfnhAKwBRdniZmldDctqR81%2F9Rzk%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20241214T013550Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTYWK7NNPZE%2F20241214%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=9cef4d9504ae741f4591f8122cf19f3cb8e8c9017cb2f80faeb68e582ed5966e&hash=7d27286bb1934712cb484af70ca0b6589ac9284f2f34781ef87100c10007c484&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0957417421012781&tid=spdf-569ff6de-d7a7-4f80-9199-85cc87335702&sid=ed6405dd1336624aa18a597772c9d71985a8gxrqa&type=client&tsoh=d3d3LnNjaWVuY2VkaXJlY3QuY29t&ua=171659035307565204&rr=8f1a75a63ce86363&cc=us)
-  https://blog.langchain.dev/benchmarking-question-answering-over-csv-data/
	- [ ] https://github.com/langchain-ai/langchain-benchmarks?tab=readme-ov-file
-  https://blog.langchain.dev/benchmarking-rag-on-tables/
-  https://docs.cloud.llamaindex.ai/llamaparse/getting_started/python
	- [ ] https://github.com/run-llama/llama_cloud_services/tree/main/examples/parse
-  https://python.langchain.com/docs/how_to/tool_results_pass_to_model/
- https://blog.langchain.dev/memory-for-agents/
- https://docs.smith.langchain.com/evaluation/how_to_guides/compare_experiment_results
- https://www.youtube.com/watch?v=0i9NzY_b3pg
- https://python.langchain.com/docs/how_to/lcel_cheatsheet/#invoke-a-runnable
- https://www.kaggle.com/code/ksmooi/langgraph-question-answering-system-ai-agent
- https://youtu.be/l7lvoiCvcVU?si=TBzufVs9xmojL0Kx