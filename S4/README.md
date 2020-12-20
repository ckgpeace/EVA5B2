### Name of the pyhton notebook - Session4_6.ipynb
## 
#### 1. Total Number of parameters used - 16,338
#### 2. Accuracy achivieved on test - 99.48% in 9 epoch

### Recipe that I tried and played and worked to reduce the number of parameters, increase in accuracy of from the vanilla model are
1. Batch Normalization
2. Only one Maxpool layer
3. Not using padding in deeper layers
4. Starting to train with small number of channles as images are not complex in MNIST dataset
5. Using GAP layes
6. Using 1X1 convulation for reducing features maps/channels in the last layer
7. No FC layes

Thanks
