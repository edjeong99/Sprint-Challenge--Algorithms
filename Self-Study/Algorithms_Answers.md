Add your answers to the Algorithms exercises here.

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```

--> O(n), each loop, n x n is increased. so it loops n times

```
b)  sum = 0

    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```

--> the 3 loops would be n to the power of 3.
the 2nd and 3rd loop is getting smaller as it runs and the last loop is always runs 9 times. But for large size of n, smaller loop and multiply by 9 would be insignificant, so the complexity would be n to the power of 3. so the O(n^3)

```
c)  def bunnieEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

--> it's recursive but only calls n times.
so O(n)

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also
that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get
broken if dropped off a floor less than floor _f_. Devise a strategy to
determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the
runtime complexity of your solution.

'''

1. if there are more than 2 floor, go to step 3
2. if there is only 1 floor left, throw egg. If egg is broken, one floor below is the answer. If eff is not broken, this is the answer. finish program.
3. from given floor, pick middle floor, throw egg
4. if egg is broken, throw away middle floor and all higher floor than middle floor, use only remaining floor and repeat 1
5. if egg is not broken, throw away all floor lower than middle floor, use only remaining floors and repeat 1

runtime complexity would be O(log n)
each step get rid of half of N, so the runtime increase much less than increase of N
