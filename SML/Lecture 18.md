## Convolutional Auto-Encoders
Encoding: Input, say $I\in \mathbb{R}^{M\times N\times1}$ $\xrightarrow{Conv. (K,(3\times3))}$ $M\times N\times K \xrightarrow{activation}$ +max pooling. (maybe $2\times 2$) (to downsample) add more layers with conv blocks and pooling.
Note, here $K$ number of kernels/filters exist which are supposed to train.

Decoding: Upsample, maybe ReLu, again upsample till you reach input dims. (obviously)$\rightarrow \hat I$
Here, $2\times 2$ upsampling is defined as $[a]\rightarrow\begin{bmatrix}a&a\\a&a\end{bmatrix}$.

We might use MSE loss. We might also use Spacial Parameter Pooling (SPP) to preserve structural integrity of input.

For the classification part (assuming the previous network is trained), Input -> encode -> flatten -> [learnable] activate + softomax (+multi class cross entropy)
**How about we change our objective to something in GAN space (to keep it more identiafiable)**

AE can help when you have limited labelled data.

___
## Model Ensembling (random forest regressors lol)
- Eww Decision trees (but easy to interpret). In theory decision spaces could be arbitary hyper-shapes.
- Since the trees (in practice) divides stuff in high dimensional rectangular regions we can create a loss function like $\sum_{j=1}^J\sum_{i\in R}(y_i-\hat{y_R})$
- But that's sad, sad in reverse is das, and das not good.
- Discretize the splits. The split across dimension $x_n$ which gives the lowest error for regionwise class will be the split to go with. For the next split, you can only choose one among the split regions (random, therefore we use forests or a hive mind lol). Apply iteratively (but thresh it lol, otherwise every sample will have it's own region). Threshing can be like, no. of samples $\geq$ for each class.
- Classification trees (loss Gini Index $G=\displaystyle\sum_{k=1}^{K}\hat{p_k}(1-\hat{p_k})$ for each node 'm', 'K' is the number of classes and $\hat{p_k}$ is the probability of 'k' in current node.).