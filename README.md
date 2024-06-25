# Thesis
**Generator:** Spawn fake images like the dataset img. **AIMs:** outsmart the descriminator 
**Descriminator:** check if the image is from the generator or the dataset. **AIMS:** better detective
Equilibrium: Generator genrates perfect fake img, Descriminator guesses  p=.5 confidence  the generator(Real/Fake)
>**Notations**
**D(x): binary classifier**  outputs(proba.) x from training data. inputs(3x64x64 RGB img). HIGH if x real, LOW if x fake
**z:** latent space vector from standard normal distribution.
**G(z):** maps z to data-space. Estimate the distribution that the training data is from ($P_{data}$) so to generate fake samples from the estimated distribution ($P_{g}$)
**D(G(z)):** the proba that out of G is Real img. 
**D -G minmax game:** D tries to maximize prob it correctly classifies Real & Fake (LogD(x)) 
        G minimizes the prob that D will predict it outputs are Fake (Log(1-D(G(z))))
$$min_{G}max_{D}V(D, G) = E_{x\~P_{data}} [logD(x)] + E_{z\~P_{z}}[log(1-D(G(z)))]$$
In theory when $P_{z}=P_{data}$ is the solution
> **DCGANs:**
D: strided Conv layers+ BatchNorm+LeakyRelu (inputs: 3x64x64 --- outputs: Proba that data are real)
G: ConvTranpose + BatchNorm + Relu (inputs: standard normal distribution _z_ --- outputs: 3x64x64 RGB img)
# Thesis
Some Documentations
