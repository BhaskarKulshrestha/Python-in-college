### Find the recurrence relation and initial conditions for the number of bit strings of length n that do not have two consecutive 0s. How many bit strings are there of length five?

   We need to think about how we can form desired bit strings from shorter bit strings with the same property. Suppose you had a bit string of length 7 with no consecutive 0s. Something like: 1011011 or 0101110. How could you form bit strings of length 8 from those? Well, you could tack on a 1 or 0 to either of them:

  1011011 ==> 10110111 or 10110110

  0101110 ==> 01011101 or 01011100

  Oops! The by tacking on a 0 to the second string, we formed a string with consecutive 0s! Why did this happen? Because 0101110 ends in a 0. It didn’t happen with 1011011 because that string ends in 1. Ok, so this suggests that we should (temporarily) break this problem into 2 problems:

  Let An = number of bit strings with no consecutive 0s that end in 1

  Let Bn = number of bit strings with no consecutive 0s that end in 0

  How do we get more A-type strings? Well, we could append a 1 to an A string or a B string. To get B strings? You have to start with an A string and append a 0 (can’t put a 0 on a B string because it will have two 0s).

  So:

  A(n+1) = A(n) + B(n)

  B(n+1) = A(n)

  But since B(n) = A(n-1) we can substitute into the recurrence relation for A(n+1):

  A(n+1) = A(n) + A(n-1)… hey, that looks familiar!

  Ok, almost done. We actually want Cn = total number of desired bit strings = An + Bn, and we need to find the base cases.

  Cn = An + Bn = A(n+1) = A(n) + A(n-1) = C(n-1) + C(n-2)

  A(1) = 1 (1), A2 = 2 (01, 11), B1 = 1 (0), and B2 = 1 (10).

  And so C(1) = 2 and C(2) = 3.

  Edit:

  Forgot to get C(5) = C(4) + C(3) = 13

  C(4) = C(3) + C(2) = 8

  C(3) = C(2) + C(1) = 5

  Quick check: bit strings of length 5 with no consecutive 0s:

  11111, 11110, 11101, 11011, 11010, 10111, 10110, 10101, 01111, 01110, 01101, 01011, 01010 - 13 as expected.
