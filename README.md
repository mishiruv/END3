**Step 1 : Construct and visualise the neural network, initialize the weights randomly** <br />
Initialize the weights randomly, usually with mean 0 and variance 1. The small scale helps in better convergence.<br />
Below is a screenshot of the neural network and the randomly assigned weights.<br />
![Screenshot](./Screenshot.png)
<br /> <br />

**Step 2 : Perform forward propagation** <br />
In each layer, perform the following operations in order to carry out forward propagation, until you receive the final output (in our case, a_o1 and a_o2) : <br />
1. Multiply the inputs with the respective weights to calculate the dot product for each neuron in the next layer. <br />
   Ex : h1 = w1*i1 + w2*i2 <br />
2. A non linear activation function is then applied to the dot product to produce the output of the neuron. This helps to maintain non linearity and complexity across the network enabling it to learn complex tasks. <br />
   Ex : a_h1 = σ(h1) = 1/(1 + exp(-h1)) [Sigmoid Activation function]<br />
<br />

**Step 3 : Calculate the error / loss** <br />
After we receive our output, we can measure how different it is from expected output using a loss function. In our case, we have used square loss function.<br />
   E1 = 1/2 * (t1 - a_o1)**2 <br />
   E2 = 1/2 * (t2 - a_o2)**2 <br />
   E_tot = E1 + E2 <br />
<br />

**Step 4 : Change the weights to minimise the loss** <br />
Since loss is a non linear function of weights, weights can be modified to minimise the loss by using gradient descent.<br />
   Ex : w1 = w1 - lr*∂E_t/∂w1 <br />
Where lr stands for learning rate. lr helps to control the rate of change of weights, so as not to overdo it. <br />
For convenience, we can use the chain rule for calculating partial derivatives. <br />
   Ex : ∂E_t/∂w5 = dE_t/∂o1 * ∂o1/dw5 <br />
Update all weights simultaneously. <br />
<br />

**Step 5 : Repeat steps 2, 3, 4 with same inputs and updated weights in each iteration** <br />
Over training, the loss will decrease as shown in Fig. Screenshot. <br />
<br />

**What happens if we change the learning rate ?** <br />
As we keep increasing the learning rate, the drop in loss gets sharper. Please see the figures below : <br />
lr : 0.1 <br />
![lr = 0.1](./lr_0.1.png) <br />
lr : 0.2 <br />
![lr = 0.2](./lr_0.2.png) <br />
lr : 0.5 <br />
![lr = 0.5](./lr_0.5.png) <br />
lr : 0.8 <br />
![lr = 0.8](./lr_0.8.png) <br />
lr : 1.0 <br />
![lr = 1.0](./lr_1.0.png) <br />
lr : 2.0 <br />
![lr = 2.0](./lr_2.0.png) <br />
<br />

Group 21 members : <br /><br />

Mohammed Yaseen (47.yaseen@gmail.com)<br />
Mayank Singhal (singhal.mayank77@gmail.com)<br />
Ravi Vaishnav (ravivaishnav20@gmail.com)<br />
Sundeep Joshi<br />
