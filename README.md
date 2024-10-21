# improvedaco

<img width="762" alt="Screenshot 2024-10-12 at 10 05 28 PM" src="https://github.com/user-attachments/assets/cb39b0de-21c7-4f64-a7b1-92a10f8ae389">

Improved Ant Colony Optimization Algorithm using a positional-encoded transformer to predict optimal pheromone matrices before running the algorithm. 



The intention of this enhancement was to use transformers to predict an optimal initial pheromone matrix from ACO. 
Finding an optimal initial pheromone matrix means it would take fewer runs to find optimal paths for ACO. 



We first collect data of normal ant colony optimization runs for cyclic graphs of different sizes, and collect its distance and pheromone matrices. 

A positional-encoded transformer is then fed the distance matrix data and then outputs a sequence of embeddings for each node. 

We then multiply this sequence by its transpose, getting a square matrix that represents the relationship between each node. 

This matrix is compared with the actual pheromone matrix of the original cyclic graph, and a MSE loss function compares the differences. 

This loss function trains the transformer to output matrices similar to pheromone matrices. 

The Improved Ant Colony Optimization Algorithm is then initialized with a pheromone matrix outputted by the transformer. 


In this experiment, we compared the performance of the normal ACO with the transformer ACO over 1500 runs, and compared their performance.



Link: [https://colab.research.google.com/drive/1ucnDXzhK37yN4M59ZXuYFYLXWxByMG6h?usp=sharing](https://colab.research.google.com/drive/1zvC6XIUUloqWqaJu4aEEFTlLwh4cS5_g?usp=sharing)
