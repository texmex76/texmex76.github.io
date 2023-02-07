---
layout: post
title:  "Convolution Cheat Sheet"
date:   2023-02-07 09:31:40 +0200
categories: machine learning
custom_css: citation
---


# Introduction

The paper {% cite bib:dumoulin2016guide %} provides a great overview. You can view the convolution animations on their [Github](https://github.com/vdumoulin/conv_arithmetic).

# PyTorch

```python
>>> inp = torch.randint(low=0, high=256, size=(16, 3, 7, 7)) / 255 # random image
>>> w = torch.rand(6, 3, 3, 3) # 3x3 kernel, 3 in-channels, 6 out-channels
>>> res = torch.nn.functional.unfold(inp, (3, 3))
>>> res.shape
torch.Size([16, 27, 25])
```

```python
>>> res = res.transpose(1, 2).matmul(w.view(w.size(0), -1).t()).transpose(1, 2)
>>> # (16, 25, 27) @ (27, 6) -> (16, 25, 6)
>>> res.shape
torch.Size([16, 6, 25])
```

```python
>>> res = torch.nn.functional.fold(res, (5, 5), (1, 1))
>>> # 7 - 3 + 1 = 5
>>> res.shape
torch.Size([16, 6, 5, 5])
```

```python
>>> torch.allclose(torch.nn.functional.conv2d(inp, w), res)
True
```

# References

{% bibliography --cited_in_order %}

<script type="text/javascript">
let listy = document.getElementsByClassName("bibliography")[0];
for (let i = 0; i < listy.children.length; i ++) {
  tmp = listy.children[i].innerText.replace(/^\[\d+\]/, "");
  listy.children[i].innerText = tmp;
}
</script>
