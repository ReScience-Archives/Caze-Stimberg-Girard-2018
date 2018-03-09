We want to thank the reviewers for their well-intentioned and valuable
comments. We describe here how we change the manuscript to adress their
comments.  

> There's a small typo in the code README, last section on parallelization
> reads 'multiple CPU cores a moder computer provide'.

We corrected the typo.  

> In Figure 2 (of the replication), I appreciate the switch from the
> epsilon+subscript axis labels used in the paper to plain text, which
> avoids having to read the caption. In line with that, I think using full text
> for inhibitory and excitatory (instead of Inh and ext) would be even clearer.

We modified the axis name to have full text inhibitory et excitatory

> Apologies if I missed it, but I don't understand why the replication of Figure 3c is
skipped. I understand that the crux of the matter is captured by a and b, but
was there a particular reason why it was omitted (e.g. computation time)?  We
added the third panel.  I would encourage, in the concluding Discussion
section, a brief recap of the differences found (detail in Figure 2,
underestimation in Figure 3) before discussing the potential causes.  We
modified the discussion accordingly I haven't gone through the details of the
derivation of the semi-analytic solution yet, but I think it would be useful to
have a sentence or two specifying if/where the derivation presented differs
from the original one.  The difference lays in how we sample the voltage
distribution otherwise we did a similar computation I don't fully agree with
the the statement that the semi-analytical result underestimates the numerical
one, if anything to me it looks shifted to the right (underestimates before the
peak, overestimates after).  We corrected the text, the difference stem wgqwweee
think from the estimation of voltage distribution.  I am slightly confused by
how you obtain a numerical approximation of P(V) as opposed to how the original
paper does it. From what I understand, you build 50 linear networks and 50
nonlinear networks (with random connectivity )and simulate each network once
for 250ms (but from how it's written it could sound as though you are running
multiple simulations of the same two networks - i.e. with the same
connections), whereas in the original they build 100 random networks (50 and
50) and simulate each ten times. Could you clarify what simulations you are
running to estimate P(V) and how they compare to what the original paper does?
It may also be good to address this difference in the paper, as you have done
in most other cases.  We clarified this point in the main text Edit: I think my
confusion in the point above may also be partly due to the fact that when you
say 'a network is simulated n times' you mean that also new random connectivity
is generated in each simulation (whereas for me intuitively simulating a
network n times means keeping the architecture and drawing new initial
potentials). This becomes clear since elsewhere you say: 'Each network was
simulated 10 times with different initial conditions (synaptic connections and
initial membrane potential values)'. It may be good to be explicit for clarity
We now further clarify this point.  Major issue: First, while many of the
decisions made by the authors have been explained, such as the choice of Brian
and certain parameter adjustments, I am missing an explanation for why the
authors decided not to use the original analytical solution as well.
Furthermore, differences between this Figure (3) and the original that are
described are too short. Instead of only replicating the figure and describing
a "good match", I would like to see a more quantitative comparison (e.g.,
position of the maximum, intersections, etc.). The same applies to Fig. 2 (see
below).  Minor issues: Manuscript: Nice introduction. In line 2, there should
be a comma after "However". Maybe, a final sentence could summarize the main
findings of the replication.  Methods are very intuitive and sufficiently
described. On page 1, I would suggest removing "dynamic" after membrane
potential. Also, in my personal opinion, often used comments in brackets
disturb the flow of reading.  In Eq. 1, I would reformat the brackets encasing
the nonlinear function to be larger.  On page 2, there is a period mark missing
when describing the spike train function \epsilon.  Why is the equation for the
nonlinearity function not numbered? I would also suggest moving the commas
after the cases. After "otherwise" there should be a period mark.  When
describing the biological observation of nonlinearity only affecting
synchronous spikes, I would like to see references.  Fantastic description of
what the neuron model effectively is (point neuron with a single nonlinear
dendrite) I enjoyed reading the argumentation for a clock-driven model with
finite precision in terms of biological plausibility.  The description for
implementing the nonlinear networks could be rewritten to match closer the
mathematical definitions. Start with describing the use of the clipping
function to achieve the nonlinearity function, then explain that ve is used as
a placeholder variable equivalent to x from the equation.  Nice description and
use of the joblib package.  In describing the grid search, I would write: "For
the grid search presented in Fig. 2, we varied inhibitory and excitatory
synaptic weights between 0.16 mV and 0.4 mV. Given that each neuron receives on
average 150 excitatory and 150 inhibitory inputs, this corresponds to an
average total weight between [...]" Below on page 4, there is a space missing
for "50 ms".  The derivation of the semi-analytical approach is well derived
and described sufficiently.  I would add to the Eq. 6 description, that it is
the expected value of spiking neurons in the next iteration given a certain
initial synchronous pulse (g_i^').  Results section describes the similarities
between original and replication sufficiently, but mainly in qualitative terms.
In Fig. 1, I would suggest using similar yticks for the rate and the number of
synchronous spikes, as well as the xticks for the time. This allows a much
better quantitative evaluation of the reproducibility of the original study.
In Fig. 2, the description of the resulting color code is very elucidating, as
this was not very well explained in the original study.  I would like to
suggest to explain, why the C panel from the original study has not been
replicated and further the differences could be described in more detail. I
also see differences for large weights (both exc. and inh.), as well as
qualitative differences for the linear network (no yellow line/areas). In B,
the area of unstable activity before stimulation seems to be significantly
larger.  Why did the authors not try the initial random spikes in transit?
Fig. 3 I discussed in the major point above.  Code: Well written, a bit
under-commented, but clearly structured The easy installation of requirements
and use of CL options make the code very reusable and in general user-friendly
In lib.py, I am a bit puzzled about the way how the function "run_with_cache"
is defined. Why can't the run function be decorated with @mem.cache as for the
other functions?  Could the authors elaborate on the definition of V0 in line
81. It does not seem to be included in Table 1 or the main text.  On first run,
I got thrown a ton of FutureWarnings concerning the use of certain dtypes in
Brian. I think this is related to the version/system I was using (although I
used the requirements.txt to get the exact version numbers). I omitted the
warnings by using the Warnings library to ignore any FutureWarnings I then
performed the simulations using the --long option, which finished after 7h38m.
