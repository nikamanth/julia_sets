# julia_sets

This is a package to generate Julia Sets. Consider a rational function in the complex plane R(z) = P(z)/Q(z) where P, Q are polynomials without common divisors. Let S be the set of points z in the complex plane that do not approach infinity after having R repeatedly applied. That is

R(R(...R(z)...))

does not go to infinity. Julia sets are the boundary of S.

[Wikipedia definition](https://en.wikipedia.org/wiki/Julia_set)

#Usage

The following is a short example on how to use this package to visualize Julia Sets.

<p><code>
using julia_sets
</code></p>
<p><code>x = [i for i=-5:0.1:5]</code></p>
<p><code>y = [i for i=-5:0.1:5]</code></p>
<p><code>function F{T<:Number}(z::T) z^2 end</code></p>

<p><code>A = gen_jset(F,x,y,10,20)</code></p>

<p><code>show_jset(A)</code></p>



