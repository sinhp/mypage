---
title: "A topos without points"
author: Sina Hazratpour
excerpt: "An example of a topos (from logic) that does not have any points."
category: research notes
tags: topos, points, sup-topology, atoms, ultrafilter
permalink: /scribbling/22-11-2017-a-topos-without-points
collection: notes
type: "scribbling"
date: 22-11-2017
use_math: true
location: "Birmingham,UK"
---


{% include macro %}


## Points

A _point_ of a Grothendiek topos $\cat{E}$ is a geometric morphism $\Set  \rightarrow \cat{E}$; if we write $\cat{E}$ as the 
classifying topos $\Set[\thT]$ of some geometric theory $\thT$ then the points of $\cat{E}$ are in one-to-one correspondence with the models of $\thT$ in $\Set$. We say a Grothendiek topos $\cat{E}$ has enough points if the inverse image of points $p: \Set → \cat{E}$ are jointly conservative. $\cat{E} = \Set[\thT]$ has enough points precisely when $\thT$ has enough models. 


### A topos with no points  

Let $B$ be complete [Boolean algebra](https://ncatlab.org/nlab/show/Boolean+algebra). Here, completeness is categorical completeness which means $B$ has all limits (i.e. meets). Note that any complete poset is necessarily cocomplete. Consider [locale](https://ncatlab.org/nlab/show/locale) $L_B$ whose corresponding [frame](https://ncatlab.org/nlab/show/frame) $O(L_B)$ is $B$. We now construct a [site](https://ncatlab.org/nlab/show/site) on $B$ by introducing a [basis](https://ncatlab.org/nlab/show/Grothendieck+pretopology) $\cat{K}$ for a [Grothendieck topology](https://ncatlab.org/nlab/show/Grothendieck+topology). 

First, notice that a sieve $S$ on an element $c$ of $B$ is nothing but a downward closed subset of ideal generated by c, i.e. $\downarrow (a)$. Declare for a sieve $S$ on $c$, $S \in \cat{K}(c)$ iff $\bigvee S = c$.  The topology generated by this basis is called the _sup-topology_ and we denote it by $\cat{J}_ {sup}$. We then consider topos of sheaves on site $(B,\cat{J}_ {sup})$ and prove it does not have any points.

The way we proceed to show that $\Sh(B,\cat{J}_ {sup})$ does not have any points is through a process called localic reflection. That is we can assign to any topos, its localic reflection $L(\cat{E})$, the locale which has the frame $Sub_{\cat{E}}(1)$ as frame of opens. If the topos $\cat{E} = \Sh (L)$ is localic, then we do not lose any information in the process of localic reflection; that is to say we have an isomorphism of frames $Sub_{\cat{E}}(1) \cong L $. Moreover, the localic reflection is a functor which is left adjoint to the functor which assigns a to locale its topos of sheaves. For any two locales $L$, $L'$ one has a natural equivalence of categories: 

$$ \mathbb{Loc}(L,L') \rightarrow \mathbb{Geom}(\Sh(L),\Sh(L'))$$

So the points of $\Sh((B,\cat{J}_ {sup}))$ correspond exactly to the points of locale $L_B$ which are in bijection with [completely prime filters](https://ncatlab.org/nlab/show/completely+prime+filter) of $B$. Now, any prime filter of a Boolean algebra is in fact an ultrafilter. (Simply because $1 = a \vee \neg a$ is in the prime filter so either $a$ is in the prime filter or $\neg a$.) For a completely prime filter $P$ of $B$, since $B$ is complete one can easily show that $\bigwedge P$ is indeed an atom of $B$: Suppose $x \in B$ with $x \le \bigwedge P$. So $x$ is not in $P$. Therefore $\neg x \in P$. Thus $ x \le \bigwedge P \leq \neg x$.
This implies $x = x \wedge \neg x = \bot$.  

Conversely, if $a$ is an atom of Boolean algebra $B$, then the principal filter $\uparrow (a)$ is an ultrafilter and hence a compeltely prime filter, and thus a point of $\Sh(B,\cat{J}_ {sup})$. 

In summary, for an atomless Boolean algebra, $\Sh(L_B)$ is a topos without any points. For an example of an atomless Boolean algebra consider the <strike>frame</strike> Boolean algebra of regular open sets of $\mathbb{R}^n$. The negation is got by taking interior of complement. Regular open means an open set whose complement's interior is equal to itself. The intuition is that regular opens do not have holes. One easily checks that this Boolean algebra does not have any atoms. 

**Remark** In general one can define an element of a Heyting algebra to be regular whenever $\neg \neg x = x$, where by definition $\neg x = x \implies \bot$. Thus a Boolean algebra is precisely a Heyting algebra in which every element is regular. 
{: .notice}  



