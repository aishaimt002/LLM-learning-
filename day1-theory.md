# Day 0 Theory: How AI Systems Work

Sources: Google Machine Learning Crash Course (intro), 3Blue1Brown neural network video, OpenStax Introduction to Python Programming (ch. 1-2).

## 1. AI, ML, DL and LLM

- **AI (artificial intelligence):** making computers do tasks that normally need human intelligence, such as understanding language, recognising images or making decisions.
- **ML (machine learning):** a part of AI where the computer learns patterns from data instead of being given fixed rules by a programmer.
- **DL (deep learning):** a part of ML that uses neural networks with many layers to learn complex patterns.
- **LLM (large language model):** a model built using deep learning. Its type of neural network is called a transformer. It is trained on huge amounts of text to predict the next token. It finds patterns in text and predicts what comes next, and that is how it produces text, code and summaries. It can sound fluent and still be wrong.

Relationship: AI contains ML, ML contains DL, and LLMs are models built with DL.

## 2. How a neural network works

- A neural network is made of layers of **neurons**. Each neuron holds a number between 0 and 1, called its **activation**.
- Example from the video (reading handwritten digits): the input layer has 784 neurons (one per pixel of a 28x28 image), then hidden layers, then an output layer of 10 neurons, one for each digit 0-9. The output neuron with the highest activation is the network's answer.
- The whole network is a function: 784 numbers go in, 10 numbers come out.
- Each neuron's activation is computed with:

  `activation = sigmoid(w1*a1 + w2*a2 + ... + wn*an + b)`

  - `a1 ... an` are the activations of the previous layer.
  - `w1 ... wn` are the **weights**: how strongly each input affects this neuron.
  - `b` is the **bias**: how easy or hard it is for this neuron to activate.
  - **sigmoid** squashes the result into the range 0 to 1.
- **Learning** means finding good values for all the weights and biases. The network in the video has about 13,000 of them.

## 3. Training and inference

- **Training:** the model reads a huge amount of text. At each position it predicts the next token, compares its guess with the real one, measures the error (the loss), and adjusts its weights to make the error smaller. This repeats a very large number of times. The model's parameters improve step by step.
- **Inference:** using the finished model. The weights are fixed and do not change. The model takes the input (your prompt) and produces output using the weights it already has. It does not learn from your prompt.

## 4. Tokens and API cost

- A **token** is a small piece of text. The input is split into tokens (for example "explain", "machine", "learning"). A token is roughly 3-4 characters of English, and long or rare words can be several tokens. The model predicts the next token from the previous tokens.
- **API cost** is the money paid to use the model through its API. It depends on tokens:

  `cost = (input tokens x input price) + (output tokens x output price)`

  Prices are quoted per million tokens, and input and output have different prices. The context window is also measured in tokens.
- Current prices: check Anthropic's pricing page (not copied here because they change).

## 5. Unsure / revisit in Week 3

- Why the output layer has 10 neurons
- How weights and bias work in the maths
- What exactly is learned during training
