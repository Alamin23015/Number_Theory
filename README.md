# Number_Theory
# Number Theory & Prime Numbers Summary
IT:23025

## Part 1: Number Theory & Cryptography (`Day 1.pdf`)
* **Euclid's Algorithm (GCD):** `gcd(a, b) = gcd(b, a mod b)` for `a >= b > 0`[cite: 56]. Runs in at most `log₂(a) + log₂(b)` iterations.
* **Extended Euclid's Algorithm:** Finds integers `x, y` such that `a*x + b*y = gcd(a, b)`[cite: 50].
* **LCM:** `lcm(a, b) = (a * b) / gcd(a, b)`.
* **Diophantine Equations:** `a*x + b*y = c` has integer solutions iff `gcd(a, b) | c`[cite: 87]. From one solution `(x₀, y₀)`, all solutions are `x = x₀ + t*q` and `y = y₀ - t*p` (where `a = d*p, b = d*q, d = gcd(a, b)`)[cite: 102, 111].
* **Modular Inverse & Division:** Inverse exists iff `gcd(a, n) = 1`[cite: 133]. Using `n*t + a*s = 1`, modular division is `b / a ≡ b * s (mod n)`.
* **Chinese Remainder Theorem (CRT):** If `gcd(a, b) = 1` and `a*x + b*y = 1`, the unique solution `n (mod a*b)` to `n ≡ r_a (mod a)` and `n ≡ r_b (mod b)` is `n = r_a * b*y + r_b * a*x`[cite: 194, 209].
* **Fast Modular Exponentiation:** Computes `b^e (mod m)` using binary representation of `e` and repeated squaring in at most `2 * log₂(e)` multiplications.
* **Fermat's Little Theorem:** If prime `p` does not divide `a`, `a^(p - 1) ≡ 1 (mod p)`[cite: 256].
* **Euler's Totient & Theorem:** `φ(n)` counts integers in `[0, n - 1]` coprime to `n` (`φ(p) = p - 1`, `φ(p*q) = (p - 1)(q - 1)`)[cite: 287, 292, 294]. If `gcd(a, n) = 1`, then `a^φ(n) ≡ 1 (mod n)`.

## Part 2: Prime Numbers (`Day 2.pdf`)
* **Infinitude of Primes:** Proved via Euclid's proof (`∏pᵢ + 1`)[cite: 311], `n! + 1`, harmonic series divergence, Fermat numbers (`2^(2^n) + 1`), and Filip Saidak's proof.
* **Distribution:**
  * **Dirichlet's Theorem:** Infinitely many primes of form `a*k + b` iff `gcd(a, b) = 1`[cite: 316].
  * **Prime Number Theorem:** Asymptotically, `π(x) = x / log x`.
* **Conjectures:** Goldbach (`even > 3 = p₁ + p₂`)[cite: 318], Waring (`odd > 3` is prime or sum of 3 primes), Twin Primes, and a prime between `n²` and `(n + 1)²`.
* **Primality Testing:**
  * **Sieving & Trial Division:** Check primes `<= √n` (optimized with Wheeling)[cite: 322].
  * **Fermat's Test & Carmichael Numbers:** Composite numbers where `a^n ≡ a (mod n)` for all `a` (e.g., `561, 1105, 1729`).
  * **Lucas' & `n - 1` Tests:** `n` is prime if for prime factors `q` of `n - 1`, `a^(n - 1) ≡ 1 (mod n)` and `a^((n - 1)/q) ≢ 1 (mod n)`.
  * **Lucas-Lehmer Test:** Tests `2^p - 1` using `l(1) = 4`, `l(n) = l(n - 1)² - 2`[cite: 330].
* **Special Numbers:**
  * **Mersenne Primes (`2^n - 1`) & Perfect Numbers** (`6, 28, 496, 8128`).
  * **Antiprimes:** Numbers with more divisors than any smaller positive integer; total divisors `d(n) = (a₁ + 1)(a₂ + 1)...(aₖ + 1)`
 
  * positive (k) for which (a^k\equiv1\pmod n), when (\gcd(a,n)=1). A primitive root has order (\phi(n)).

8. Lucas and Related Primality Tests
The slides state a Lucas criterion based on the prime factors of (n-1), and mention the (n-1) test, Pepin's test, Proth's theorem, Lucas–Lehmer test and (n+1) tests. These advanced criteria are described in the notebook; not all are implemented.

9. Mersenne Primes and Lucas–Lehmer Test
A Mersenne number is (M_p=2^p-1). For prime (p>2), the Lucas–Lehmer sequence is:

[ s_0=4,\qquad s_{i+1}=s_i^2-2. ]

(M_p) is prime exactly when (s_{p-2}\equiv0\pmod{M_p}). The notebook implements this test for small prime exponents.

10. Perfect Numbers
A perfect number equals the sum of its positive proper divisors. The first examples are 6, 28, 496 and 8128. The notebook computes proper-divisor sums and checks these examples.

11. Antiprimes / Highly Composite Numbers
A highly composite number has more positive divisors than every smaller positive integer. If (n=\prod p_i^{a_i}), its divisor count is:

[ d(n)=\prod_i(a_i+1). ]

The notebook computes divisor counts and lists record-holders up to a chosen limit.

12. Fundamental Theorem of Arithmetic and Applications
Every integer greater than 1 has a unique prime factorization, up to the order of factors. The lecture connects prime numbers with number-theoretic functions, modular arithmetic, cryptography, rings and algebraic number theory.
