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
