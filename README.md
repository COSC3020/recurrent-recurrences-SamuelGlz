[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$T(n) = T(\frac{n}{13} +5)$

$= T(\frac{\frac{n}{13}}{13} +5) + 5$

$= T(\frac{n}{13^2} +5 + 5)$

The pattern is as follows:

$T(n) = T(\frac{n}{13^i} + 5 * i)$

Solving for n:

$13^i = n$

$log_{13}13^i = log_{13}n$

$i = log_{13}n$

Substituting back in:

$T(n) = T(\frac{n}{13^{log_{13}n}} + 5 * (log_{13}n))$

$= T(1) + 5*log_{13}n$

$= 1 + 5*log_{13}n$

T(n) $\in$ log(n)

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$T(n) = 13 T(\frac{n}{13} +5)$

$= 13(13T(\frac{n}{13^2}) +5) + 5$

$= 13^2 T(\frac{n}{13^2}) + 13*5 + 5$

$= 13^3 T(\frac{n}{13^3}) + 13^2 * 5 + 13 * 5 + 5$

The pattern is as follows:

$T(n) = 13^i T(\frac{n}{13^i}) + \sum_{j = 1}^{i}{13^{j-1}*5}$

Solving for n:

$13^i = n$

$log_{13}13^i = log_{13}n$

$i = log_{13}n$

Substituting back in:

$T = 13^{log_{13}n} T(\frac{n}{13^{log_{13}n}}) + \sum_{j = 1}^{log_{13}n}{13^{j-1}*5}$

$= n * T(\frac{n}{n}) + \sum_{j = 1}^{log_{13}n}{13^{j-1}*5}$

$= n * T(1) + \sum_{j = 1}^{log_{13}n}{13^{j-1}*5}$

$= n + \sum_{j = 1}^{log_{13}n}{13^{j-1}*5}$

The sum will just end up as a constant, which is asymptotically irrelevant  

T(n) $\in$ n

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

$T(n) = 13 T(\frac{n}{13} + 2n)$

$= 13(13T(\frac{n}{13^2}) + \frac {2n}{13}) + 2n$

$= 13^2 T(\frac{n}{13^2}) + 2n + 2n$

The pattern is as follows:

$T(n) = 13^i T(\frac{n}{13^i}) + (2*i)n$

Solving for n:

$13^i = n$

$log_{13}13^i = log_{13}n$

$i = log_{13}n$

Substituting back in:

T(n) = $13^(log_{13}n) T(\frac{n}{13^{log_{13}n}})$ + $2(log_{13}n)*n$

= n * T(1) + $2(log_{13}n)$ * n

= n + $2(\log_{13}n)$ * n 

T(n) $\in$ n * log(n)
