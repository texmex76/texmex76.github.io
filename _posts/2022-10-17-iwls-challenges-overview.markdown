---
layout: post
title:  "IWLS Challenges Overview"
date:   2022-10-17 09:07:40 +0200
categories: logic synthesis
custom_css: citation
---


# Introduction

According to their [website](https://www.iwls.org/), "The **I**nternational **W**orkshop on **L**ogic and **S**ynthesis is the premier forum for research in synthesis, optimization, and verification of integrated circuits and systems.". I would like to give an overview of the 2020, 2021 and 2022 challenges by mostly providing links (the challenge content is all over the place and I found it hard to find stuff).

# 2020 Challenge

Given were several, freshly constructed [benchmarks](https://github.com/iwls2020-lsml-contest/iwls2020-lsml-contest/tree/d686782bcd1a25272560e156a60edef226878edf/benchmarks) or in other words, training sets. The training sets had features of $\mathbb{B}^n$, where $\mathbb{B}$ denotes the set {0, 1} and labels $\mathbb{B}$, so a binary classification task. The challenge was to come up with an AIG with a maximum of 5000 nodes for each training set that represents a good fit.

Contest description is [here](https://github.com/iwls2020-lsml-contest/iwls2020-lsml-contest/blob/6205e1bc5780521a7feb9920714f65809f1adcc1/contest_description.pdf).

They made a paper {% cite bib:rai2021logic %} out of the contest results.

# 2021 Challenge

This time, the task was to come up with AIG classifiers that fit [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) well. Input were 32x32 8-bit 3-channel color images, so 24576 in total and there are 10 output classes. There were 3 "leagues"; a maximum of 10,000, 100,000 and 1,000,000 nodes.

Call for contest is [here](https://www.iwls.org/contest/2021/IWLS21_Call_for_Contest.pdf).

They only made [slides](https://www.iwls.org/contest/2021/IWLS21_Contest_Slides.pdf) out of the contest results, no paper.

The [winning team](https://www.youtube.com/watch?v=ZX48kUy_KPU) used XGBoost which they converted into circuit, the [2nd team](https://youtu.be/hN9aFaw7wCc) started out with a CNN and the [3rd team](https://youtu.be/mVI0AMYjP6Y) used random forests for 10,000 and 100,000 nodes and a CNN for 1,000,000 nodes.

The graphic below is taken from the [contest website]()

{:refdef: style="text-align: center;"}
![iwls 2021 contest results](https://www.iwls.org/contest/2021/2021_gallery.png){: width="800"}
{:refdef}

# 2022 Challenge

The 2022 contest was about exact logic gate synthesis, so given a truth table, construct an AIG. There was no node limit, but fewer nodes gave more points.

Contest announcement is [here](https://github.com/alanminko/iwls2022-ls-contest/blob/main/IWLS_2022_Programming_Contest.pdf).

Again no paper, but some [slides](https://github.com/alanminko/iwls2022-ls-contest/blob/main/IWLS_2022_Contest_Presentation.pdf).

The [contest GitHub](https://github.com/alanminko/iwls2022-ls-contesti) contains the benchmarks and circuit submissions.

Video from [the winners](https://youtu.be/qUnB-01oMiQ), the [2nd team](https://www.youtube.com/watch?v=tK6SVAF2gMU) and [3rd team](https://www.youtube.com/watch?v=BumyhlIKnHY).

# References

{% bibliography --cited_in_order %}

<script type="text/javascript">
let listy = document.getElementsByClassName("bibliography")[0];
for (let i = 0; i < listy.children.length; i ++) {
  tmp = listy.children[i].innerText.replace(/^\[\d+\]/, "");
  listy.children[i].innerText = tmp;
}
</script>
