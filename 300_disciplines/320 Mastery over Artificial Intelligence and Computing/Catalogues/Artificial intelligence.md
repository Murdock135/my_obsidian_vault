
# Appendix

## Learning resources

- [ ] #book Art of computer Programming
- [ ] #docs Bash [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html)
- [x] #docs vimtutor
- [ ] #docs vimtutor sequel
- [ ] #book https://guide.bash.academy/
- [ ] #book Deep learning Bible
- [ ] #book PRML (bishop)
- [ ] #book Foundations of Machine Learning (Shai Shalev)
- [ ] #book Linear Algebra (Sheldon Axler)
- [ ] #book Linear Algebra (Howard Anton)
- [ ] #book Statistical Inference (Casella)
- [ ] #book Computational intelligence (Rudolf Kruse)
- [ ] #book On Neural Differential Equations
- [ ] #book Computer Systems: A Programmer's Perspective
- [ ] #book Modern Operating Systems by Tanenbaum
- [ ] #book [The twelve factor app](https://12factor.net/)
- [ ] #book Beyond the twelve factor app
- [ ] #blog Python3 module of the week https://pymotw.com/3/
- [ ] #repo [xbeat machine learning repo](https://github.com/xbeat/Machine-Learning)
- [ ] #docs [Github learning resources](https://docs.github.com/en/get-started/start-your-journey/git-and-github-learning-resources#online-courses)
- [ ] #docs [Github get started](https://docs.github.com/en/get-started)
- [ ] #docs[Huggingface](https://huggingface.co/docs)
- [ ] #course [Course on Parallel processing by Stanford CS149](https://www.youtube.com/playlist?list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp)
## Essential Topics
This is list is ever-growing.
1. RNNs
2. LSTMs
3. Transformers
4. ~~Large Language Models~~
5. Deep metric learning
6. GANs
7. ResNet
8. KAN (Kolmogorov Arnold networks)
9. Bayesian Neural Net
10. CNN
11. C-means
12. PCA
13. tSNE
14. Decision Tree
15. Random Forest
16. Autoencoder
17. Bayesian Neural Network
18. Sparse data methods
19. SVD
20. SVM
21. Eigen decomposition
22. 
## Tools
### 1. Dev Tools and Libraries
19. Docker
20. Git
21. Python debugger (pdb)
22. Kubernetes
23. Bash 
24. Python
25. Pandas
26. Numpy
27. Langchain
28. Tmux
29. Neovim
30. Huggingface
31. Elixir
### 2. Data related
26. PostgreSQL
27. SQLAlchemy
28. [Datahub]([The #1 Open Source Metadata Platform | DataHub](https://datahubproject.io/))

# FAQ
1. Why not c++ instead of python?
	Machine learning is inherently data intensive, and typical ML algorithms are massively data-parallel. Therefore, even when developing new algorithms, high-level mathy languages (like Python, R, [Octave](https://www.quora.com/Why-does-Andrew-Ng%E2%80%99s-Machine-Learning-course-use-Octave-instead-of-R)) can be reasonably fast if you are willing to describe your algorithm in terms of standard operations on matrices and vectors.

	On the other hand, for deeper exploration of fundamental concepts it can be more interesting to treat individual components as _objects_ for which you want to conceptualize and visualize their internal state and interactions. This is a case where C++ may shine. Using C++, of course, means that a compiler will attempt to optimize your execution speed. Additionally, it opens the door to straightforward multi-core execution with [OpenMP](https://en.wikipedia.org/wiki/OpenMP) (or [other available threading approaches](https://stackoverflow.com/q/23258037/86967)).
	
	C++ is a high level language -- not inherently more verbose or tedious than Python for algorithm development. The biggest challenges for working with C++ are:
	
	- A more anarchic library ecosystem means a bigger effort for choosing and integrating existing components.
	- Less stable language rules (or the interpretation thereof) means that something you create today might not compile a few years down the road (due to compiler upgrades).
	
	Consider, also, that TensorFlow documentation identifies some benefits of using C++ over Python for certain low-level cases. See [TensorFlow: Create an op](https://www.tensorflow.org/guide/create_op).
	
	---
	
	Low-level coding for GPU acceleration is an entirely different can of worms with very limited language options. This is not something to be concerned about until _after_ you have a well-defined custom algorithm that you want to super-optimize. More likely, you would be better off using a framework (like TensorFlow) to handle GPU interactions for you.
	
	---
	
	For exploratory visualization purposes, don't discount the interactive power of JavaScript, which is also comparatively fast:
	
	- [A Neural Network Playground](https://playground.tensorflow.org/)
	- [TensorFlow.js demos](https://www.tensorflow.org/js/demos/)
	- [ConvNetJS: Deep Learning in your browser](https://cs.stanford.edu/people/karpathy/convnetjs)
2. 