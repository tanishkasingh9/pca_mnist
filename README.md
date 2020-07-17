# Applying PCA on MNIST 

Pricipal Component Analysis (PCA) also known as Karhunen-Loeve transform, is widely used for the purpose of dimensionallity reduction, feature extraction, and data visualization. It provides a way for lossy data compression, orthogonally projecting the data onto a lower dimensional space. The goal is to reduce the dimensionality from D dimensions, here 784 (28X28 image flattened), to a lower dimension M such that the variance of the projected data is maximized.

<br>
Let x represent one data points out of N examples, and mu is the mean of N data samples then the PCA will include calculating the covariance matrix S, M largest eigen values of S and the corresponding M eigen vectors represented by A:

<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\large&space;S&space;=&space;\frac{1}{N}&space;\Sigma^N_{n=1}\&space;(x_n&space;-&space;\mu)(x_n&space;-&space;\mu)^T\\" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\large&space;S&space;=&space;\frac{1}{N}&space;\Sigma^N_{n=1}\&space;(x_n&space;-&space;\mu)(x_n&space;-&space;\mu)^T\\" title="\large S = \frac{1}{N} \Sigma^N_{n=1}\ (x_n - \mu)(x_n - \mu)^T" /></a> 
  <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=\large&space;A^TSA&space;=&space;\lambda\\" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\large&space;A^TSA&space;=&space;\lambda\\" title="\large A^TSA = \lambda\\" /></a>
  <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=\large&space;X_{new}&space;=&space;A^T.X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\large&space;X_{new}&space;=&space;A^T.X" title="\large X_{new} = A^T.X" /></a> 
</p>

After PCA for reducing the dimension from 784 to 10, the covariance of the data points looks like following:
<p align="center">
  <img src="https://raw.githubusercontent.com/tanishkasingh9/pca_mnist/master/PCAcovar.png">
</p>

On PCA whitening, or on calculating <a href="https://www.codecogs.com/eqnedit.php?latex=\small&space;W.X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\small&space;W.X" title="\small W.X" /></a>, we can see the lossy compression of the images:

<p align="center">
  <img src="https://raw.githubusercontent.com/tanishkasingh9/pca_mnist/master/b4.png">
</p>

## Result of Classification 
Reduced to two dimensions using PCA 
<p align="center">
  <img src="https://raw.githubusercontent.com/tanishkasingh9/pca_mnist/master/2d.png">
</p>

Result of Fisher's LDA analysis:
<p align="center">
Metric Description| Result
--- | --- 
|training accuracy  |  93.0%|
|Class 0 (true label = 5) training accuracy |  95.5\%
|Class 1 (true label = 8) training accuracy |  90.5\%
|test accuracy  | 71\%
|Class 0 (true label = 5) test accuracy  |  6.0\%
|Class 1 (true label = 8) test accuracy  |  94.0\%

</p>




