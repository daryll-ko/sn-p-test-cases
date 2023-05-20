# `sn-p-test-cases`

Hello! This repo holds all test cases for evaluating Spiking Neural P (SN P) system simulations.

## Downloading test cases

You can download all existing test cases by visiting the `Releases` section and downloading the `{release}-sn-p-test-cases.zip` archive attached to the latest release.

<img src="assets/downloading_test_cases_sample.png" />

## Test case list

| Name                                 | Function                                                                                                               | Source                                                                          |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `positive_integer_generator`         | generates $`\{k \mid k \ge 2\}`$ using nondeterminism                                                                  | [Leporati et al.](https://link.springer.com/article/10.1007/s11047-022-09917-y) |
| `even_positive_integer_generator`    | generates $`\{2k\mid k \ge 1\}`$ using nondeterminism                                                                  | [Păun](https://cs.ioc.ee/yik/schools/win2007/paun/snppalmse.pdf)                |
| `boolean_triple_sum_not_2\|b1,b2,b3` | if $`in_{i}`$ is constantly provided with bit `bi`, there is an output spike at $`t = 3`$ iff $`b1 + b2 + b3 \ne 2`$   | [Păun](https://cs.ioc.ee/yik/schools/win2007/paun/snppalmse.pdf)                |
| `increment\|v`                       | increment the number in the register neuron $`r`$ by $`1`$ (a neuron containing $`2k`$ spikes represents number $`k`$) | [Leporati et al.](https://link.springer.com/article/10.1007/s11047-022-09917-y) |
