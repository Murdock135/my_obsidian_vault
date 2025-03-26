# Milestones
- [ ] #milestone Create agentic system.
- [ ] #milestone Review Fuzzy expert system project.
- [ ] #milestone Create Fuzzy expert system.
- [ ] #milestone Set up an ETL infrastructure for extracting, transforming and loading data. Use APIs to download data where possible instead of downloading data.
- [ ] #milestone Test all code coded so far (Jan 2025)
- [ ] #milestone Finish reading open ai's cookbook
- [ ] #milestone Read the entire langchain website

# Pillars
- Data uniformization and merging.
- Exploratory Data Analysis.
- Agentic system for root-cause analysis.
- Missing data handling.

# Tasks
- [x] #tasks Review your langchain learning scripts #ongoing ✅ 2025-02-11
- [ ] #tasks Give the questions to an LLM and ask it to categorize based on the context #ongoing
- [ ] #task Make example reasoning steps with team.
- [ ] #tasks Complete langchain course 
- [x] #task Learn CSV-langchain #ongoing ✅ 2025-01-04
- [ ] #task Set up a huggingface 'datasets' repo for storing the data. Write in your readme.md how data should be downloaded and where it should be kept (data should be downloaded into `data/` but add this directory to the `.gitignore` file so that any changes made to this folder isn't pushed to the data repository).  This will guard against others trying to manipulate the data in unwanted ways.  #ongoing
- [ ] #task create a schematic of the langchain system 
- [ ] #task Read about FAISS
	- [x] #task Read the github README #ongoing ✅ 2025-03-17
	- [ ] #task Read the github wiki #ongoing 
- [x] #task create an ETL pipeline ✅ 2025-03-15
- [x] #task Make slides for half day meeting #planned ✅ 2025-03-05
- [ ] #task Change the `requirements.txt` file so that the requirements are platform specific. 
- [ ] #task Use APIs from openrouter
- [ ] #task Set up system message for the agent.
- [ ] #task Talk to Dr. A about new resource allocation project for salmonella.
- [ ] #task Talk to Dr. A about experiments to run about the LLM
- [ ] #task Talk to Dr. A about expert system.
- [x] #task Make presentation for meeting 1-15-2025 #ongoing ✅ 2025-01-23
	- [x] #task Include dataset name in presentation. ✅ 2025-01-15
- [x] #task Find LLM validation methods #ongoing ✅ 2025-01-15
- [x] #task Fill up 6 month plan form #planned ✅ 2025-02-07
- [x] #task Fill up Data sources form #planned ✅ 2025-01-15
- [ ] #task Log transformations in preprocessing files 
- [ ] #task Test preprocessing and merging pipelines #ongoing
	- [x] #task Config.py ✅ 2025-01-06
	- [x] #task data_preprocessing.py #ongoing ✅ 2025-01-07
	- [x] #task utils.py ✅ 2025-01-07
	- [x] #task setup.py ✅ 2025-01-14
	- [ ] #task scripts/preprocessing/merge_datasets.py
	- [ ] #task scripts/preprocessing/expand_merged.py
- [ ] #task Run pipeline for 2020, 2021, 2022 
- [ ] #task Create a list of variables in excel #planned
- [x] #task Get API keys for openAI, lanchain and tavily #ongoing ✅ 2025-01-03
- [ ] #task Create rules for FIS
- [x] #task consolidate meeting notes ✅ 2025-01-23
- [x] #task Create a demo of CSV-langchain querying ✅ 2025-01-04
- [x] #task Discuss where to store data #ongoing ✅ 2025-01-31
- [ ] #task Find and Read Review papers on agentic systems.
# Ramblings
 We need a halfday meeting demonstrating LLM and expert system.
- How to deal with comments within NORS dataset (This may help formulate the system message of the agentic system)
- Vijay needs to know the input, output format
- How do we store the data that is used by the LLM?
- Make the LLMs scrape the web as well.
- Can we use causal discovery?
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
# References
 [Argonne Researchers Win Gordon Bell Special Prize for Using Language Models to Track Virus Variants - High-Performance Computing News Analysis | insideHPC](https://insidehpc.com/2022/12/argonne-researchers-win-gordon-bell-special-prize-for-using-language-models-to-track-virus-variants/)
- [ ] [Argonne researchers win Gordon Bell Special Prize for adapting language models to track virus variants | Argonne National Laboratory](https://www.anl.gov/article/argonne-researchers-win-gordon-bell-special-prize-for-adapting-language-models-to-track-virus#:~:text=Scientists%20from%20the%20U.S.%20Department,identifying%20how%20a%20virus%20evolves.)
- [ ] [GenSLMs: Genome-scale language models reveal SARS-CoV-2 evolutionary dynamics](https://www.biorxiv.org/content/10.1101/2022.10.10.511571v1.full.pdf)
- [ ] [Protein Generation via Genome-scale Language Models with Bio-physical Scoring](https://dl.acm.org/doi/pdf/10.1145/3624062.3626087)
- [ ] [[2310.04607] A Comprehensive Performance Study of Large Language Models on Novel AI Accelerators](https://arxiv.org/abs/2310.04607)
- [ ] [CSV | 🦜️🔗 LangChain](https://python.langchain.com/v0.1/docs/use_cases/sql/csv/#%EF%B8%8F-security-note-%EF%B8%8F)
- [ ] [An integrated deep learning and stochastic optimization approach for resource management in team-based healthcare systems](https://pdf.sciencedirectassets.com/271506/1-s2.0-S0957417421X0019X/1-s2.0-S0957417421012781/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjECoaCXVzLWVhc3QtMSJIMEYCIQCx6X2aU47F%2BSVWklnSFhBY35EUrvGvIQqN%2BgWfBYPG8wIhAKUsDJVed6ETOI3Bd8w7Mx05sIsb5tbK22nFiWvlFchqKrsFCOL%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQBRoMMDU5MDAzNTQ2ODY1IgyUfby4f%2BS0wAw%2FzwYqjwX2LbNDra%2FuNZsQ%2FgOIAcjm7%2Fuf5cpMsWj422RpmRjZrMPQwMd8OEbyqN5n6HF16cfiRohxCzuPVK1dnFniB0AaYo4QqbvTIELB4GQWYIOblEu6dhZXzTsC1ixmo%2BJhi0ScgE7wQq3Kl%2F09SuKwvsQR9X27QM4%2BaGlDPNjeBSZnIUx6Lf9VhfBKZg1cnj3F10tpo8G7wm0OV0SDJwuiMlgyJNJdjUxk6uy%2B9oGX7U%2FaTUGDS%2F4ZGswjO9CnPfp38Oyxis7reqIrgcTS%2FR3h%2FbVQfoBCrLVaJVYloR9oZwS6WwDIrUYgRCQ3Ei%2FbvfuhiEdeflUqR9Nw%2FikP6G%2BgFOMmlwhDDN3oleRIqqmrzsk3P9NRUSkyVYpPZlXNTMPz2mOeMPXGRqVG0BUVBnojlYbXcGSJiAtwJAZ8x68J2UU5s6Ly0hWlfPzIG66RjQI5KG%2FIR44KJJSGMECj6lifQ44VRFBoAjqoKxcGbuDry1Z%2Bq9ugGj6cvpST%2FS8YQtftpr0G91f%2FxvPAQoQhkH99%2FG15ufGBXX8WOr4UzHE4oDo7U4%2FzdBwzNu5FgXXJrrp2g5vHE8%2FoLvjsJqzrTf7sg5MiqTkbEuWDgzeOwxjAuSUm4%2Few0TAPqUDID7WepNWm0SltCnyyin9pI6li9m4saP4YZfcGeK4lgMMaIaVdBqFsQJXf8me98H4JBpCmPTeY6VRun98u5qANOJn3ln2Vcoic2urC6GMJxSXz%2BasmUDOeFUVXj2RdFjSOaq6YYOHbQI8hShgO8aYmBaA00AwIYtHDnLW4gGfPPZ2yuTF6VSYGUsOHGekT3AZ9a9y%2F4ovix%2FJuDzRr2iaZ3U3dC8TzEhVPK9hmjBG6kWrrwe3WxXZUMKG087oGOrABk8BAMxfq63KSRkVpYJ8kygITSUGvM%2Fdt3xXxNa1hvYTWWLFTl74%2FGm5RKbJs3Wv6uVL26dHCik5Q%2FEy6i0BEqv6Q1EU1uMU8j88Cp6wrXtMOq8pIz9ezvYmzoddsT7%2BTrUM%2ByALxackQ%2Ff9Qyv9C8mEF1zKYySuLbghJsy6j8gNScJC7jFAcmV%2B8SbfghzDkvRJMH%2FWw4FG5uqnYfnhAKwBRdniZmldDctqR81%2F9Rzk%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20241214T013550Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTYWK7NNPZE%2F20241214%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=9cef4d9504ae741f4591f8122cf19f3cb8e8c9017cb2f80faeb68e582ed5966e&hash=7d27286bb1934712cb484af70ca0b6589ac9284f2f34781ef87100c10007c484&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0957417421012781&tid=spdf-569ff6de-d7a7-4f80-9199-85cc87335702&sid=ed6405dd1336624aa18a597772c9d71985a8gxrqa&type=client&tsoh=d3d3LnNjaWVuY2VkaXJlY3QuY29t&ua=171659035307565204&rr=8f1a75a63ce86363&cc=us)
- [ ] https://blog.langchain.dev/benchmarking-question-answering-over-csv-data/
	- [ ] https://github.com/langchain-ai/langchain-benchmarks?tab=readme-ov-file
- [ ] https://blog.langchain.dev/benchmarking-rag-on-tables/
- [ ] https://docs.cloud.llamaindex.ai/llamaparse/getting_started/python
	- [ ] https://github.com/run-llama/llama_cloud_services/tree/main/examples/parse