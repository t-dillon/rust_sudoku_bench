This is a fork of Emerentius/sudoku adding a dynamic library for use with the benchmark program in t-dillon/tdoku.

Below are benchmark results on several data sets for this (rust_sudoku), two other JCZSolve-family solvers (the
original JCZSolve and SK_BFORCE2), and Tdoku. See https://github.com/t-dillon/tdoku/tree/master/benchmarks for
a more complete set of comparisons.

<pre>
|puzzles0_kaggle                  |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |   597,337.3 |         1.7 |     100.0% |           0.00 |
|sk_bforce2                       | 1,238,657.3 |         0.8 |     100.0% |           0.00 |
|rust_sudoku                      |   886,884.8 |         1.1 |        N/A |            N/A |
|tdoku_dpll_triad_simd            | 1,025,631.6 |         1.0 |     100.0% |           0.00 |

|puzzles1_17_clue                 |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |   290,454.3 |         3.4 |      69.6% |           1.90 |
|sk_bforce2                       |   378,453.4 |         2.6 |      73.8% |           1.01 |
|rust_sudoku                      |   412,494.2 |         2.4 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |   341,523.8 |         2.9 |      78.7% |           0.61 |

|puzzles2_magictour_top1465       |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |    78,107.4 |        12.8 |       2.3% |          20.73 |
|sk_bforce2                       |    86,641.5 |        11.5 |       3.6% |          15.43 |
|rust_sudoku                      |    95,658.9 |        10.5 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |   120,903.9 |         8.3 |       7.9% |           9.06 |

|puzzles3_forum_hardest_1905      |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |    16,257.2 |        61.5 |       0.0% |         138.78 |
|sk_bforce2                       |    18,114.3 |        55.2 |       0.0% |         103.28 |
|rust_sudoku                      |    19,761.3 |        50.6 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |    24,855.5 |        40.2 |       0.0% |          54.99 |

|puzzles4_forum_hardest_1905_11+  |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |    12,629.1 |        79.2 |       0.0% |         171.17 |
|sk_bforce2                       |    14,328.7 |        69.8 |       0.0% |         122.63 |
|rust_sudoku                      |    15,466.6 |        64.7 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |    20,727.1 |        48.2 |       0.0% |          64.93 |

|puzzles5_forum_hardest_1106      |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |     6,628.8 |       150.9 |       0.0% |         365.89 |
|sk_bforce2                       |     7,256.1 |       137.8 |       0.0% |         270.92 |
|rust_sudoku                      |     8,316.7 |       120.2 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |    13,224.2 |        75.6 |       0.0% |         113.10 |

|puzzles6_serg_benchmark          |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         |   310,837.4 |         3.2 |       0.0% |           7.09 |
|sk_bforce2                       |   348,996.9 |         2.9 |       0.0% |           7.08 |
|rust_sudoku                      |   429,979.7 |         2.3 |        N/A |            N/A |
|tdoku_dpll_triad_simd            |   407,731.4 |         2.5 |       0.0% |           7.13 |

|puzzles7_gen_puzzles             |  puzzles/sec|  usec/puzzle|   %no_guess|  guesses/puzzle|
|---------------------------------|------------:| -----------:| ----------:| --------------:|
|jczsolve                         | 1,797,646.1 |         0.6 |      97.4% |           0.31 |
|sk_bforce2                       | 2,080,316.6 |         0.5 |      97.5% |           0.29 |
|rust_sudoku                      | 1,508,323.6 |         0.7 |        N/A |            N/A |
|tdoku_dpll_triad_simd            | 3,106,185.7 |         0.3 |      97.4% |           0.29 |
</pre>

Run on i5-8600k clang-8 -O3 -march=native
