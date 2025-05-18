This is just a practice on vision transformer, I have used the VideoMAE for binary classification, for that "UCF101 subset" dataset has been used.
The result at the end, Test Accuracy=0.813.

### Vision Transformer VideoMAE

1. First divides the video into 3D patches and linearly project them into an embedding vector.
2. Then adds the positional vectors (spatial + temporal) with the linear projections of the patches.
4. To this sequence adds a classification token, this one is added to get the final classification output.
5. This is then passed to the transformer architecture.
6. This transformer only contains the encoder part from the original architecture, each encoder consists of Norm, Multi Head Self Attention (Joint Space-Time), Norm, MLP and the usual residual connections.
7. At last a final MLP is applied on the Extracted CLS token, followed by Softmax. Result would be a vector of C dimension, C being the number of classes.
