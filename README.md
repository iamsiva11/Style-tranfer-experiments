# Style Transfer experiments

## Style Transfer Components
* 2 inputs - content image, style image
* Loss functions - content loss, style loss, total variation loss
* Gram-matrices


## Pseudocode/Steps

1/ Compute  4 losses(neural style loss)
gram matrix, style loss, content loss,total variation loss

2/ combine these loss functions into a single scalar

3/ compute loss and gradients

4/ Run L-BFGS optimisation over the pixels of the generated image so as to minimize the neural style loss


### Optimisation problem

Style transfer problem can be posed as an optimisation problem, where the loss function we want to minimise can be decomposed into three distinct parts: the content loss, the style loss and the total variation loss.

```
x* = argmin(x)(α*content_loss(c,x) + β*style_loss(s,x))

{c - content image , x - combined image/output , s - style image}
{α and β are simply numbers that allow us to control how much we want to emphasise the content relative to the style.}
```

## Important keywords
Gram Matrix , content representation.


## Notes on Loss functions

### Style loss

The loss-function for the style-image is slightly more complicated, because it instead tries to minimize the difference between the so-called Gram-matrices for the style-image and the mixed-image. This is done at one or more layers in the network. The Gram-matrix measures which features are activated simultaneously in a given layer. Changing the mixed-image so that it mimics the activation patterns of the style-image causes the colour and texture to be transferred.




### Content loss

The content loss is a L2 distance between the features of the base
image (extracted from a deep layer) and the features of the combination image,keeping the generated image close enough to the original one.

### Total variation loss

The total variation loss imposes local spatial continuity between
the pixels of the combination image, giving it visual coherence.In other words, a regularisation term that encourages spatial smoothness.



## Papers

[A Neural Algorithm of Artistic Style](http://arxiv.org/abs/1508.06576)

[Stable and Controllable Neural Texture Synthesis and Style Transfer Using Histogram Losses](https://arxiv.org/abs/1701.08893)