---
layout: post
title: On Pyro - Deep Probabilistic Programming on PyTorch
---

Pyro, a "deep universal probabilistic programming language" on
PyTorch, was announced today (see [blog post](https://eng.uber.com/pyro/); [homepage](http://pyro.ai)).
People were curious of my thoughts. I shared a short note on
[reddit](https://www.reddit.com/r/MachineLearning/comments/7ak6x9/n_uber_ai_labs_open_sources_pyro_a_deep/),
copied and pasted below:

> This is great work coming from the Uber AI labs, especially by Eli Bingham and Noah Goodman for leading this effort among an excellent group. I've met with them in-person on numerous occasions to discuss the overall design and implementation details. Pyro touches on interesting aspects in PPL research: dynamic computational graphs, deep generative models, and programmable inference.
>
> It's yet to see where Pyro will come to fruition. Personally, inheriting from my advisors David Blei and Andrew Gelman, I like to think from a bottom-up view where applications ground design principles; and they end up determining the direction and success of a PPL. For Stan, it's hierarchical GLMs fueled with HMC across a variety of social and political sciences. For Edward, it's deep latent variable models fueled with black box VI across text, images, and spatial data. I'd like to see where Pyro not only makes dynamic probabilistic programming easier, but (1) what applications it enables that was not possible before; and (2) what new PPL innovations come out. Attend, Infer, Repeat ([Pyro notebook](https://github.com/uber/pyro/blob/dev/tutorial/source/air.ipynb)) is a great example in this direction.
>
> On speed: Pyro might be faster than Edward on CPUs depending on the intensity of graph-building in PyTorch vs TensorFlow. I'm confident Edward will dominate on GPUs (certainly TPUs) when data or model parallelism is the bottleneck. It warrants benchmarks, including Pyro vs native PyTorch. Edward benefits from speed being just as fast as native TF because the underlying computational graph is the same. Dynamic PPLs trade off that benefit.
