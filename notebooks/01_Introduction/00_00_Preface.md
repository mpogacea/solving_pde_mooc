---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.5.2
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

<!-- #region -->

<p style="text-align: center; font-size: 24pt;  "> Numerical methods for partial differential equations</p>

<p style="text-align: center; font-size:18pt;  "> Bernard Knaepen & Yelyzaveta Velizhanina</p>
</br>
</br>
</br>

# Introduction

## Philosophy of the course

Numerous scientific problems can only be addressed through modeling and computer analysis. This stems from the fact that a lot of these problems are complex and we cannot solve the corresponding models using only pen-and-paper. 

Many models appearing in engineering or physical applications are mathematically described by partial differential equations (PDEs) and the aim of this course is to provide a practical introduction to the relevant tools to solve them using computer algortihms. By practical we mean that we will not develop the theory behind PDEs and also avoid complex mathematical derivations of the numerical methods we describe below. Although these are beautiful subjects, they are often characterized by a steep learning curve and our objective is to get our hands on solving real problems as quickly as possible. In some places we nevertheless provide some mathematical background about the techniques we describe because they cannot be properly understood otherwise. In each case, we try to keep things simple and written in such a way that the corresponding section may be skipped at first reading.

## Outline

By the end of the course, the student should have acquired the necessary skills to solve numerically equations such as the heat equation or Schrödinger's equation:

\begin{align*}
\frac{\partial T(\boldsymbol r,t)}{\partial t}  & = \alpha \Delta T(\boldsymbol r,t), &\hbox{Heat equation}\\
i\hbar \frac{\partial \Psi(\boldsymbol r,t)}{\partial t} & = \left[ \frac{-\hbar^2}{2m}\Delta + V(\boldsymbol r,t) \right]\Psi(\boldsymbol r,t), &\hbox{Schrödinger equation}
\end{align*}

We don't further describing those equations here (it's not a problem if you have never heard about them), but we just emphasises that they both contain the laplacian operator

\begin{equation*}
 \Delta = \frac{\partial^2}{\partial x^2}+ \frac{\partial^2}{\partial y^2}+ \frac{\partial^2}{\partial z^2}
\end{equation*}

that makes them partial differential equations. Our main objective is then to formulate such operators numerically and to solve the resulting problems with computer algorithms. This also requires to complement the equations with suitable boundary conditions and to implement them consistently with the differential operators.

This course covers the following topics:

- <u>*Integration of ordinary differential equations:*</u>
ordinary differential equations (ODEs), unlike partial differential equations, depend on only one variable. The ability to solve them is essential because we will consider many PDEs that are time dependent and need generalizations of the methods developped for ODEs 


- <u>*Finite difference schemes:*</u>
in this chapter we describe the most intuitive way of computing spatial derivatives. It heavily relies on the Taylor's expansion of functions and how we can use the information in the neighborhood of a point to compute derivatives at that point.


- <u>*Resolution of partial differential equations:*</u> this part of course combines the concepts discussed in the first two chapters and describes through examples how they can be used to solve PDEs.


- <u>*Iterative methods:*</u> many of the techniques involved in solving ODEs or PDEs require to invert matrices. For low dimensional matrices, this can be done through standard elimination methods. For large matrices, such methods are prohibitively expensive and some approximate inversion techniques are needed. In this chapter we describe some of them belonging to the class of iterative methods. 

- <u>*Fourier transform:*</u> in the chapter about finite difference schemes we have described an intuitive way to compute spatial derivatives. Here we introduce a more accurate technique that relies on the expansion of the unknown functions using a basis of functions. We illustrate the concepts introduced to solve problems with periodic boundary conditions.
 
- <u>*Chebyshev discretisation:*</u> we conclude this course by giving a brief introduction on the Chebyshev spectral method. It also relies on the concept of Fourier transforms but the expansion basis is constructed using Chebyshev polynomials. This method is very accurate and well adapted to problems with physical boundaries as opposed to problems with periodic boundary conditions.

## Tools

The numerical resolution of PDEs obviously requires the use of a programming language and optionally some previously developped software packages. For this course we have decided to use the Python programming language and some of the SciPy (Scientific computing tools for Python) packages. In the next notebook - 00_01_ToolkitSetup - we say a few more words about this and also provide a complete set of instructions to install all the necessary tools required to get started with the course.


<!-- #endregion -->

```python

```