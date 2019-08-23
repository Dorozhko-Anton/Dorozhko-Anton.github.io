---
layout: post
title:  "Test post utils"
categories: [blog, travel]
tags: [hot, summer]
d3: True
---

* Except for commonly used abbreviations (U.S., a.m.), spell out a term
to be abbreviated the first time it is used, followed by the abbrevia-
tion in parentheses. Thereafter, the abbreviation may be used alone.
* In long documents, repeat the full term in parentheses after the ab-
breviation at regular intervals to remind readers of the abbreviation’s
meaning, as in “Remember to submit the CAR (Capital Appropriations
Request) by. . . .”

<!--more-->


## Code highlights

{% highlight python %}
print(hello)
2+2 = 4
if 1 :
  2+2 - 2
{% endhighlight %}


```c++
int hello(std::string world) {
  cout << world << endl;
  return 0
}
```

$$x^3 + \frac{1}{3}$$

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

<html>
<canvas style="width:100%;height:200px"></canvas>
</html>

$$
\begin{align*}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{align*}
$$

## Images

![image-title-here](/assets/images/404.jpg){:height="100px" width="100px"}

text for test sssssssssssssssssssssssssssssssssssssssssssssssssssssssss

![image-title-here](/assets/images/404.jpg){:height="100px" width="100px"}

![image-title-here](/assets/images/404.jpg){:height="100px" width="100px"}

![image-title-here](/assets/images/404.jpg){:height="100px" width="100px"}


## Gist

<script src="https://gist.github.com/Dorozhko-Anton/b78427bc41a72c6b0240a8bf3ac35be8.js"></script>

<script>

var canvas = document.querySelector("canvas"),
    context = canvas.getContext("2d"),
    width = canvas.width,
    height = canvas.height,
    color = d3.scaleSequential(d3.interpolateRainbow).domain([0, 1000]),
    randomX = d3.randomNormal(0.3),
    randomY = d3.randomNormal(0);

render();

canvas.onclick = render;

function render() {
  var x0 = width / 20,
      y0 = height / 2,
      mainWalk = randomWalk(x0, y0, 500);

  context.clearRect(0, 0, width, height);
  context.lineJoin = "round";
  context.lineCap = "round";
  context.lineWidth = 1.5;
  context.strokeStyle = "black";
  renderWalk(mainWalk);

  context.globalCompositeOperation = "multiply";
  context.lineWidth = 1;
  for (var i = 0; i < mainWalk.length; i += 2) {
    var branchStart = mainWalk[i],
        x0 = branchStart[0],
        y0 = branchStart[1];
    for (var j = 0; j < 1; ++j) {
      context.strokeStyle = color(i + (Math.random() - 0.5) * 50);
      var x1 = x0, y1 = y0;
      for (var k = 0, m = 20; k < m; ++k) {
        context.globalAlpha = (m - k - 1) / m;
        var pieceWalk = randomWalk(x1, y1, 10),
            pieceEnd = pieceWalk[pieceWalk.length - 1];
        renderWalk(pieceWalk);
        x1 = pieceEnd[0];
        y1 = pieceEnd[1];
      }
      context.globalAlpha = 1;
    }
  }
}

function renderWalk(walk) {
  var i, n = walk.length;
  context.beginPath();
  context.moveTo(walk[0][0], walk[0][1]);
  for (i = 1; i < n; ++i) {
    context.lineTo(walk[i][0], walk[i][1]);
  }
  context.stroke();
}

function randomWalk(x0, y0, n) {
  var points = new Array(n), i;
  points[0] = [x0, y0];
  for (i = 1; i < n; ++i) {
    points[i] = [
      x0 += randomX() * 2,
      y0 += randomY() * 2
    ];
  }
  return points;
}

</script>
