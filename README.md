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
x* = argminx(αcontent_loss(c,x) + βstyle_loss(s,x))

{c - content image , x - combined image/output , s - style image}
{α and β are simply numbers that allow us to control how much we want to emphasise the content relative to the style.}
```
