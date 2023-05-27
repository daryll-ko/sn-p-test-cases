# `sn-p-test-cases`

Hello! This repo holds all test cases for evaluating Spiking Neural P (SN P) system simulations.

## Downloading test cases

You can download all existing test cases by visiting the `Releases` section and downloading the `{release}-sn-p-test-cases.zip` archive attached to the latest release.

<img src="assets/downloading_test_cases_sample.png" />

## Test case format

Each format folder (`xml`, `json`, `yaml`) contains several systems and simulation snapshots for those systems. For each system, there's a file named $`\verb!name!`$ or $`\verb!name(inputs)!`$ for the system itself and a folder with the same name for the system's snapshots. The snapshot folder contains files named $`\verb!name[timestamp]!`$ or $`\verb!name(inputs)[timestamp]!`$.

## Test case list

All notes about probabilities below apply only for pseudorandom simulations (i.e., the simulator chooses the rule a neuron will apply uniformly at random).

| Name                                 | Function                                                                                                                                                                                                            | Source                                                                                                              | Notes                                                                                                         |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `even_positive_integer_generator`    | generates $`\{2k\mid k \ge 1\}`$ using nondeterminism                                                                                                                                                               | [Păun](https://cs.ioc.ee/yik/schools/win2007/paun/snppalmse.pdf)                                                    | probability of generating $`2k`$ is $`\dfrac{1}{2^{k}}`$                                                      |
| `multiples_of(n)`                    | generates $`\{nk \mid k \ge 2\}`$ using nondeterminism                                                                                                                                                              | [Tim & Joshua](https://docs.google.com/presentation/d/15zhdrcK5ZtFU0zP1N9stn14LsU8OclwDBRu7bYUCXCk/edit#slide=id.p) | probability of generating $`nk`$ is $`\dfrac{1}{2^{k-1}}`$                                                    |
| `boolean_triple_sum_not_2(b1,b2,b3)` | if $`in_{i}`$ is constantly provided with bit $`\verb!bi!`$, there is an output spike at $`t = 3`$ iff $`\verb!b1! + \verb!b2! + \verb!b3! \ne 2`$                                                                  | [Păun](https://cs.ioc.ee/yik/schools/win2007/paun/snppalmse.pdf)                                                    |                                                                                                               |
| `increment(v)`                       | increment the number $`\verb!v!`$ in the register neuron $`r`$ by $`1`$ (a neuron containing $`2k`$ spikes represents number $`k`$); module passes control to one of $`l_{j}`$ and $`l_{k}`$ at random              | [Leporati et al.](https://link.springer.com/article/10.1007/s11047-022-09917-y)                                     |                                                                                                               |
| `decrement(v)`                       | decrement the number $`\verb!v!`$ in the register neuron $`r`$ by $`1`$ (a neuron containing $`2k`$ spikes represents number $`k`$); module passes control to $`l_{j}`$ if $`\verb!v! > 0`$ and $`l_{k}`$ otherwise | [Leporati et al.](https://link.springer.com/article/10.1007/s11047-022-09917-y)                                     |                                                                                                               |
| `bit_adder(L)`                       | given the reversed binary representations of the elements in $`L`$, if $`S`$ is the sum of these elements, output spike train is the reversed binary representation of $`S \times 2^{\|L\| - 2}`$                   | extension of [WebSnapse v2 test cases](https://github.com/nccruel/websnapse_extended/tree/master/public/test-systems)                                                                                                                    |                                                                                                               |
| `subset_sum(L,s)`                    | halts iff there is a subset of `L` whose sum is `s`                                                                                                                                                                 | [Leporati et al.](https://core.ac.uk/download/pdf/157763961.pdf) (with minor edits)                                                   | if $`N`$ is the number of subsets of `L` whose sum is `s`, probability of halting is $`\dfrac{N}{2^{\|L\|}}`$ |
