We would like to again thank the reviewers for their valuable and constructive
comments.

In preparing the revision, we noticed an error in our plotting code. The network 
firing rate plotted in Fig.1 (middle row) was incorrectly based on a bin size of
0.1ms, instead of the 1ms that was used in the original publication (and also
stated in our figure caption). Therefore, the (non-synchronous) background
activity appeared to be 10 times lower than it actually was.

Below we describe, when needed, how we changed the code and the manuscript to
adress the reviewers' comments. 

# RW1

> There's a small typo in the code README, last section on parallelization
> reads 'multiple CPU cores a moder computer provide'.

We corrected the typo in the README file.

> In Figure 2 (of the replication), I appreciate the switch from the
> epsilon+subscript axis labels used in the paper to plain text, which avoids
> having to read the caption. In line with that, I think using full text for
> inhibitory and excitatory (instead of Inh and ext) would be even clearer.

We modified the axis labels accordingly.

> Apologies if I missed it, but I don't understand why the replication of
> Figure 3c is skipped. I understand that the crux of the matter is captured by
> a and b, but was there a particular reason why it was omitted (e.g.
> computation time)?

There was no particular reason for this choice and we have now added the
simulation and the corresponding plot to our Figure 2.

> I would encourage, in the concluding Discussion section, a brief recap of the
> differences found (detail in Figure 2, underestimation in Figure 3) before
> discussing the potential causes. 

We modified the discussion accordingly (see L434 in the .tex file).

> I haven't gone through the details of the derivation of the semi-analytic
> solution yet, but I think it would be useful to have a sentence or two
> specifying if/where the derivation presented differs from the original one.

We have now clarified this in the text. The derivation is just provided as a
more detailed description of the approach presented in the original article but
is identical. There is a potential difference in the way the observed membrane
potential distribution is used as an estimate of P(V), as the details (e.g.
number of bins for the histogram, use of interpolation/smoothing, etc.) were not
mentioned in the original article.

> I don't fully agree with the the statement that the semi-analytical result
> underestimates the numerical one, if anything to me it looks shifted to the
> right (underestimates before the peak, overestimates after).  I am slightly
> confused by how you obtain a numerical approximation of P(V) as opposed to
> how the original paper does it.

TODO: Things changed with the new correction

# RW2

## Major issue: 

> First, while many of the decisions made by the authors have been explained,
> such as the choice of Brian and certain parameter adjustments, I am missing
> an explanation for why the authors decided not to use the original analytical
> solution as well. 

We now further justify our choice in the main text(see L339 in tex file). We
found that the analytical approach was not described in as much detail as the
semi-analytical one and therefore focussed on the latter. If the reviewers think
that including the analytical solution is important, then we can contact the
original authors to have further details.

> Furthermore, differences between this Figure (3) and the original that are
> described are too short. Instead of only replicating the figure and
> describing a "good match", I would like to see a more quantitative comparison
> (e.g., position of the maximum, intersections, etc.). The same applies to
> Fig. 2 (see below).

We have added some more quantitative comparison to the results in the original
work (See L328).

## Minor issues

> The description for implementing the nonlinear networks could be rewritten to match closer the
> mathematical definitions. Start with describing the use of the clipping
> function to achieve the nonlinearity function, then explain that ve is used as
> a placeholder variable equivalent to x from the equation. 

TODO

> The C panel from the original study has not been
> replicated and further the differences could be described in more detail. I
> also see differences for large weights (both exc. and inh.), as well as
> qualitative differences for the linear network (no yellow line/areas). In B,
> the area of unstable activity before stimulation seems to be significantly
> larger.

The C panel has now been replicated and we include further details about the
quantitative differences to the original study.

> Why did the authors not try the initial random spikes in transit?

Our simulations now include initial random spikes, although the details of their
implementation was not clear from the text. (See ...)


> I got thrown a ton of FutureWarnings concerning the use of certain dtypes in
> Brian. I think this is related to the version/system I was using (although I
> used the requirements.txt to get the exact version numbers). I omitted the
> warnings by using the Warnings library to ignore any FutureWarnings

These warnings should only appear with numpy 1.14, which was released after the
latest release of Brian 2. Please double check that you are using numpy 1.13.3
as stated in requirements.txt. That said, the warnings can be safely ignored and
Brian 2 does work correctly with numpy 1.14.

