We want to thank the reviewers for their well-intentioned and valuable
comments. We describe, when needed, how we change the manuscript to adress
their comments.  

# RW1

> There's a small typo in the code README, last section on parallelization
> reads 'multiple CPU cores a moder computer provide'.

We corrected the typo in the README file.  

> In Figure 2 (of the replication), I appreciate the switch from the
> epsilon+subscript axis labels used in the paper to plain text, which avoids
> having to read the caption. In line with that, I think using full text for
> inhibitory and excitatory (instead of Inh and ext) would be even clearer.

We modified the axis name to have full text inhibitory et excitatory

> Apologies if I missed it, but I don't understand why the replication of
> Figure 3c is skipped. I understand that the crux of the matter is captured by
> a and b, but was there a particular reason why it was omitted (e.g.
> computation time)?  We added the third panel.

We added the third panel

> I would encourage, in the concluding Discussion section, a brief recap of the
> differences found (detail in Figure 2, underestimation in Figure 3) before
> discussing the potential causes. 

We modified the discussion accordingly (see L434 in the .tex file)

> I haven't gone through the details of the derivation of the semi-analytic
> solution yet, but I think it would be useful to have a sentence or two
> specifying if/where the derivation presented differs from the original one.

The semi analytical work agrees with the original work. It's the numerical
simulations that differ. (see L430)

> I don't fully agree with the the statement that the semi-analytical result
> underestimates the numerical one, if anything to me it looks shifted to the
> right (underestimates before the peak, overestimates after).  I am slightly
> confused by how you obtain a numerical approximation of P(V) as opposed to
> how the original paper does it.

We corrected the text, the difference stems from the numerical simulation
where the clocking introduce "false positive" spikes absent from a continuous
model. The numerical curve are in fact shifted upwards due to false positve
(see L430). This is due to false positive spikes.  The difference lays in how
we sample the voltage distribution otherwise we did a similar computation. We
acknowledge that details in the original work were unclear to reproduce the
analytic approach (see L333)

# RW2

## Major issue: 

> First, while many of the decisions made by the authors have been explained,
> such as the choice of Brian and certain parameter adjustments, I am missing
> an explanation for why the authors decided not to use the original analytical
> solution as well. 

We further justify our choice (see L339 in tex file). The analytical was less
explicitly described than the semi-analytical. We can contact the original
authors to have further details. We were happy to reproduce at least on the
approach, but we could try to have it reimplemented when we have further
details.

> Furthermore, differences between this Figure (3) and the original that are
> described are too short. Instead of only replicating the figure and
> describing a "good match", I would like to see a more quantitative comparison
> (e.g., position of the maximum, intersections, etc.). The same applies to
> Fig. 2 (see below).

We further explicit the differences from the original work (See L328).
@stimberg should we change the figure.2?

## Minor issues

> The description for implementing the nonlinear networks could be rewritten to match closer the
> mathematical definitions. Start with describing the use of the clipping
> function to achieve the nonlinearity function, then explain that ve is used as
> a placeholder variable equivalent to x from the equation. 

> The C panel from the original study has not been
> replicated and further the differences could be described in more detail. I
> also see differences for large weights (both exc. and inh.), as well as
> qualitative differences for the linear network (no yellow line/areas). In B,
> the area of unstable activity before stimulation seems to be significantly
> larger.  Why did the authors not try the initial random spikes in transit?
> Fig. 3 I discussed in the major point above.  

> I got thrown a ton of FutureWarnings concerning the use of certain dtypes in
> Brian. I think this is related to the version/system I was using (although I
> used the requirements.txt to get the exact version numbers). I omitted the
> warnings by using the Warnings library to ignore any FutureWarnings I then
> performed the simuluations using the --long option, which finished after 7h38m.
