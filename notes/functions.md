latex input:        mmd-article-header  
Title:              Writing Functions in R
Affiliation:        Bios301       
Author:             Christopher J. Fonnesbeck
Date:               Fall 2012
latex mode:         memoir  
xhtml header:       <script type="text/javascript"
    src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
latex input:        mmd-article-begin-doc  
latex footer:       mmd-memoir-footer 




<!-- See lecture 1 from Shalizi course -->

Rather than writing code procedurally, like a script, it is usually more efficient to discretize code into functions. This is particularly the case for code that you wish to re-use in multiple places or times. Not only does it save time and space, by not having to re-type the same sections of code in multiple places, but also reduces the likelihood of error propogation and improves the maintainability of code.

You should be familiar with functions in a mathematical sense, whereby one or more *arguments* are plugged in as values for variables in a formula, yielding an output value. Similarly, most programming languages allow for the writing of functions that encapsulate a series of calculations, usually involving argument values passed from other code, and often returning a value or data structure to be used by the caller. For example, we may write a function that estimates the parameters of a linear model, accepting predictor and response variable as arguments, and returning a vector of calculated parameters. Alternately, a function may be used to draw a graph. In this case, there is no return value *per se*, but a window may pop up containing a plot. This is known as a *side-effect*.

In R, a function can be defined using the following syntax:


    a_function <- function(an_argument, another_argument) {
        # Do something to the arguments
        value <- an_argument^2 + 3 * another_argument
        # Return the calculated value
        return(value)
    }


## A statistical function

Lets look at an example of writing a statistical function. Here, we will consider a useful, but somewhat obscure distribution: the [Pareto distribution](http://en.wikipedia.org/wiki/Pareto_distribution). The Pareto is best known for describing the 80/20 rule. Its probability distribution function is as follows:

\\[f(x|a,c) = \frac{ca^c}{x^{c+1}}\\]

where \\(a \le x < \infty\\) and \\(a,c > 0\\). The cumulative distritbution function (CDF), which describes the total probability of all values up to and including \\(x\\), is specified by:

\\[F(x|a,c) = 1 - (a/x)^c\\]

Whereas, the inverse distribution function, which returns the value of \\(x\\) for which the cumulative probability is \\(p\\), is calculated by:

\\[Q(p|a,x) = a(1-p)^{-1/c}\\]





