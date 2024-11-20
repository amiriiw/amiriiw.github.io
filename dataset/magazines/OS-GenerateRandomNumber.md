<h2 align="center">HOW COMPUTERS GENERATE RANDOM NUMBER</h2>
<p align="center">learning URLs:<a href="https://youtu.be/cwHZSu-zAcI?si=gKVxrgAe4WugEFx5">jadi</a></p>

---

# Random Number Generation

Random number generation is a crucial topic in computer science and mathematics. Since 1940, various methods for generating random numbers have been developed, which can be broadly categorized into two main types: **True Random Numbers** and **Pseudo Random Numbers**.

## 1. True Random Numbers

These numbers are generated based on natural processes and are considered completely random. Some methods for generating true random numbers include:

- **Physical Devices**: Such as radio telescopes or thermal noise generators that utilize natural noise or quantum processes.
- **Environmental Data**: Including electrical noise or fluctuations in temperature and pressure.

These methods often require specialized and expensive equipment, making them less commonly used.

## 2. Pseudo Random Numbers

These numbers are generated using algorithms and form a sequence that appears random. The most important methods for generating pseudo random numbers include:

### a) Pseudo Random Generators

- **Linear Congruential Generators (LCG)**: One of the earliest and most well-known algorithms. This method uses a linear relationship to produce numbers:
  \[
  X\_{n+1} = (aX_n + c) \mod m
  \]
  where \(a\), \(c\), and \(m\) are parameters that must be chosen carefully.
- **Mersenne Twister**: This is one of the most widely used and efficient generators, with a very long period (2²³⁹³⁷−1) and good uniform distribution properties.

### b) Non-Linear Algorithms

- **Tree-based and Search Algorithms**: Such as Random Tree or graph-based algorithms.

## 3. Methods Introduced but Not Widely Used

- **Fractal-based Algorithms**: Due to computational complexity and longer processing times, these have received less attention.
- **Quantum Random Algorithms**: Currently in research phases and not yet widely used in everyday applications.

## 4. Applications

Random numbers have various applications, including:

- **Cryptography**: For generating secure and random keys.
- **Simulation**: In statistical modeling and simulations.
- **Video Games**: For creating random scenarios and experiences.

## 5. Challenges

Generating random numbers faces specific challenges, with one of the most important being the assurance of randomness and unpredictability of the number sequences. This is especially critical in security and cryptography fields.

## 6. Conclusion

Random number generation has evolved significantly since 1940. From simple and basic methods to complex and modern algorithms, all have aimed to meet various scientific, industrial, and security needs. Over time, with scientific and technological advancements, the methods of random number generation have improved and diversified.

---
