**Alex Kimoni  
homework-02**

**1** Please answer the following questions
(a) Try the commands `pi`, `round(pi)`, `round(pi, digits = 4)`, and `trunc(pi)`, `ceiling(pi)`, `floor(pi)`. What are the results?
```R
> pi
[1] 3.141593
> round(pi)
[1] 3
> round(pi, digits = 4)
[1] 3.1416
> trunc(pi)
[1] 3
> ceiling(pi)
[1] 4
> floor(pi)
[1] 3
```
(b) Try the commands `sqrt(16)`, `16^0.5`. Are the results the same? Yes
```R
> sqrt(16)
[1] 4
> 16^0.5
[1] 4
```
(c) Write a command that computes `4^3`.
```R
> 4^3
[1] 64
```
(d) Try the commands `log10(1000)`, `log(1000)`. Then try the command `log2(64)`. What are the results? (Make sure you understand the different logarithmic functions.)
```R
> log10(1000)
[1] 3
> log(1000)
[1] 6.907755
> log2(64)
[1] 6
```
e) Look at the help page for log() by typing: `? log`. Read the first few lines. Does the text match your observations from the previous question?
$${\color{green}Yes. `log10(1000) = y` and `10^y = 1000`.Green}$$

**2** Use the following command to create a "character" vector representing a supermarket
queue with Steve first in line:



