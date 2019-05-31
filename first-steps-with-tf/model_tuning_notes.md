## Model tuning
Is There a Standard Heuristic for Model Tuning?

This is a commonly asked question. The short answer is that the effects of different hyperparameters are data dependent. So there are no hard-and-fast rules; you'll need to test on your data.

That said, here are a few rules of thumb that may help guide you:

    Training error should steadily decrease, steeply at first, and should eventually plateau as training converges.
    If the training has not converged, try running it for longer.
    If the training error decreases too slowly, increasing the learning rate may help it decrease faster.
        But sometimes the exact opposite may happen if the learning rate is too high.
    If the training error varies wildly, try decreasing the learning rate.
        Lower learning rate plus larger number of steps or larger batch size is often a good combination.    
    Very small batch sizes can also cause instability. First try larger values like 100 or 1000, and decrease until you see degradation.
Again, never go strictly by these rules of thumb, because the effects are data dependent. Always experiment and verify.
