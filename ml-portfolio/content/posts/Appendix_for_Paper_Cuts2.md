---
title: "Appendix Section of the Paper: Discovering Physical Concepts With Neural Networks Simplified 🤖✨"
date: 2025-01-11
draft: false
tags: ["AI", "Neural Networks", "VAEs", "Machine Learning"]
categories: ["Learning"]
---

## 🤖 Appendix A: Neural Networks 101

### **What’s a Neural Network?**
A neural network is like a group of friends 👫 working together. Each friend (a **neuron**) takes some inputs (e.g., gossip) and decides what’s important before passing it along. 📤

---

### **1. Single Artificial Neuron: The Basic Unit** ⚙️
Imagine one neuron is a super-smart *calculator friend*. 🧮 Here’s what it does:

1. Takes inputs ... 🖊️  
2. Multiplies them by *weights* ... 💪  
3. Adds a *bias* b , which is like its mood. 🌀  
4. Passes the result through an **activation function**, which decides how excited it gets. 🎉  

#### **Activation Function**  
For this paper, they used **Exponential Linear Unit (ELU)**:
- If the input is positive: 🟢 **Keep it as it is**.  
- If the input is negative: 🔴 **Smooth it out** using a fancy exponential formula. 🧙

---

### **2. Neural Networks: Like a Super Social Network** 🌐
When you connect lots of neurons together, you get a **neural network**. 🎛️ Here's the setup:

1. **Input Layer**: Where data comes in (e.g., numbers, images). 👀  
2. **Hidden Layers**: Where the neurons gossip and figure out patterns. 🤫  
3. **Output Layer**: Where decisions or answers are made (e.g., "cat or dog?"). 🐱🐶  

Neural networks are **universal approximators**, meaning they can learn almost anything—like a genius who just needs enough practice. 🤓🎯

---

### **3. Training: How Neural Networks Learn** 🎓🧑‍🏫

Neural networks are lazy at first (all weights and biases are random). 🎲 But during training, they adjust themselves to get better at solving problems. Here’s how:

1. **Cost Function**: Measures how bad the network's predictions are (like a test score 📉).  
2. **Gradient Descent**: The network uses feedback to adjust weights and biases, slowly improving. 💪  
   - This is like hiking downhill to find the lowest point of a valley. ⛰️⬇️  
3. **Stochastic Gradient Descent**: Instead of using the entire dataset at once, it trains in small batches (mini-study sessions). 📚  

They also use **backpropagation**, which is like a teacher correcting the network's mistakes step by step. 🧑‍🏫🔄

---

## 🤔 Appendix B: Variational Autoencoders (VAEs)

### **What’s a VAE?**
A **Variational Autoencoder** is like a super-organized librarian. 📚 It:
1. **Encodes** high-dimensional data (e.g., a huge book) into a **compact summary** (e.g., a sticky note). 🗒️  
2. **Decodes** the summary back into the full data, ensuring it makes sense. 🔄  

---

### **1. Representation Learning: Why Compress Data?** 🗜️
The goal is to turn complex input x  into a smaller representation z  while keeping all the important stuff.  
Think of it like summarizing "War and Peace" into a tweet. 🐦

- **Encoder**: Maps input x  → representation z .  
- **Decoder**: Uses z to recreate x .  

---

### **2. Probabilistic Encoder/Decoder: Adding Uncertainty** 🎲
Instead of mapping x to z deterministically, VAEs use probabilities. 🤔  
- The encoder says: “Hmm, z could be anywhere in this range.” 🎯  
- The decoder takes these probabilities and guesses the original data. 🔄  

To make this work, we assume z follows a normal (Gaussian) distribution, which makes the math nice and smooth. 📊

---

### **3. Reparameterization Trick: Solving the Math Drama** 🧙‍♂️
**Problem**: Probabilities are tricky to differentiate. 😤  
**Solution**: **Reparameterization Trick**:
1. Use random noise epsilon from a standard distribution. 🎲  
2. Transform it into the required distribution:  
    z = mu + sigma * epsilon 

Now, we can train the network like normal! 🚀

---

### **4. The beta VAE Cost Function: Keep it Organized!** 🧹✨
To train a VAE, we minimize a **cost function**:
1. **Reconstruction Loss**: How well the decoder recreates the input. 🧩  
2. **Regularization**: Encourages disentangled, independent variables in z .  

This makes z super clean, like Marie Kondo organizing a messy house. 🧹🏠

---

## 🔎 Appendix C: Interpreting Latent Variables

### **What’s a Latent Variable?**
Latent variables are like hidden clues in a mystery novel. 🔍  
In SciNet, they represent the **degrees of freedom** needed to describe the system.

**Example**: For a pendulum, the latent variables might be the damping factor and spring constant—nothing else matters! 🏋️

---

## 🔄 Appendix D: Cyclic Representations

### **What’s the Problem?**
Some data, like angles, is **cyclic** (e.g., 0 degrees= 360 degrees).  
Neural networks struggle with cyclic data because they assume all data is continuous. 📈

**Example**:
- Imagine mapping angles on a circle to a line. At 360 degrees, the line suddenly "jumps" back to 0 degrees.  
- This discontinuity makes the network go, “What the heck?!” 🤯

---

### **Real-Life Example: The Bloch Sphere in Quantum Mechanics** ⚛️
The **Bloch sphere** is used to represent qubits, but it’s cyclic:
**Latitude (theta)** ranges from 0 degrees at the equator to 180 degrees at the poles.
**Longitude (phi)** ranges from 0 degrees to 360 degrees, representing a full circle around the sphere.
 

Neural networks can’t handle the "wrap-around" behavior easily, so they approximate it with steep curves, which leads to errors. 🚨

---

### **In Summary:**
1. Neural networks = smart friends solving problems together. 🤖  
2. VAEs = librarians compressing data without losing meaning. 📚  
3. Cyclic data = troublemakers for neural networks. 🔄🌀  

