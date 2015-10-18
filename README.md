# julia_sets

This is a package to generate Julia Sets. Consider a rational function in the complex plane R(z) = P(z)/Q(z) where P, Q are polynomials without common divisors. Let S be the set of points z in the complex plane that do not approach infinity after having R repeatedly applied. That is

R(R(...R(z)...))

does not go to infinity. Julia sets are the boundary of S.

[Wikipedia definition](https://en.wikipedia.org/wiki/Julia_set)

#Usage

The following is a short example on how to use this package to visualize Julia Sets. The <code>gen_jset()</code> function that has the following properties:

Input:
* R - a rational function on the complex numbers (or just a function).
* x - a 1-D array of grid points on the real line
* y - a 1-D array of grid points on the imaginary line
* n_iter - the maximum number of iterations on a point (set a reasonable default)
* escape_tol - if the norm of a point goes beyond this tolerance, consider it gone to infinity (set a reasonable default)

Output:
* An array A of size(x) by size(y), where A[ i,j ] is the number of iterations it took z = x[ i ] + 1im * y[ j ] to surpass the escape_tol parameter in norm.  If the point did not escape, set A[ i,j ] to escape_tol + 1.

<p><code>
using julia_sets
</code></p>
<p><code>x = [i for i=-5:0.1:5]</code></p>
<p><code>y = [i for i=-5:0.1:5]</code></p>
<p><code>function F{T<:Number}(z::T) z^2 end</code></p>

<p><code>A = gen_jset(F,x,y,10,20)</code></p>

<p><code>show_jset(A)</code></p>



