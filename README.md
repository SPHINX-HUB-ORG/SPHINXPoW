# SPHINXPoW

# Introduction
This project is dedicated to the world community as an Open-source Post-quantum SPHINX blockchain, means anyone can join and contribute based on his/ her passion and skills. SPHINX is a blockchain protocol designed to provide secure and scalable solutions in the post-quantum era. The project aims to develop a robust and decentralized network using a Proof of Work (PoW) consensus algorithm initiated by the community. We thrilled to introduce a new design for Proof-of-Work operation.


# Components of SPHINXPoW

### SPHINX_256 Hash Function
The [SPHINXHash](https://github.com/SPHINX-HUB-ORG/SPHINXSign/blob/main/sphincs%2B-round3-specification.pdf)
 hash function used in the code is based on [SWIFFTX](https://github.com/ChyKusuma/SPHINXHash/blob/main/SWIFFTX_Report.pdf) which is a cryptographic hash function, the designed to provide secure hashing capabilities because its relly on `Lattice-based` that today we are knowing its promising secure in the post-quantum era. This hash function takes a message as input and produces a fixed-size output of 256 bits.


### calculateHash Function
The `calculateHash` function in the `SPHINXMiningAlgorithm` namespace is used to calculate the hash of a given message with a specified number of required leading zeros. It iterates through nonce values until it finds a hash that meets the difficulty target. The function appends the nonce to the message, calculates the hash using the `SPHINX_256` hash function, and checks if the hash meets the required number of leading zeros.

### meetsDifficultyTarget Function
The `meetsDifficultyTarget` function is a custom function used to check if a given hash meets the difficulty target. It takes the hash and the required number of leading zeros as input and iterates through the hash characters to check if the hash has the required number of leading zeros. It returns `false` if any character is not '0', indicating that the hash does not meet the difficulty target.

### solveNonce Function
The `solveNonce` function in the `SPHINXPoW` namespace is responsible for solving the nonce value for a given data and difficulty level. It iterates through nonce values and combines them with the data to mine a block using the `mineBlock` function from the `Miner` class. It then checks if the mined block's hash meets the difficulty target by calling the `meetsDifficultyTarget` function.

### adjustDifficulty Function
The `adjustDifficulty` function is used to dynamically adjust the difficulty level based on the network hash rate and other factors. It calculates the expected number of blocks per day, adjusts the target blocks per day for developer mining, and calculates the network target hash rate. It then adjusts the difficulty target by reducing or increasing the target based on the network hash rate and a predefined adjustment factor.

### Mathematical Properties
The SPHINXPoW algorithm includes several mathematical operations for nonce calculation and difficulty adjustment. This will help the algorithm safe from brute-force attacked by set up the randomness. Here are some of the mathematical properties used in the code:

- `multiply` Function: This inline function is used to multiply the upper and lower digits of a number. It takes a number `k` as input, splits it into upper and lower digits, and multiplies them. If either the upper or lower digits are zero, the function returns `k` as it is.

- `extract_32_digits` Function: This inline function extracts 32 digits from a givennumber `k`. It uses mathematical operations like `frexp`, `modf`, and casting to extract the desired digits.

- `select_and_do_operation` Function: This inline function selects and performs mathematical operations based on a sequence number (`seq`) and a given number `k`. It supports operations like division, multiplication, addition, square root, exponential, trigonometric functions, logarithmic functions, and others. The function checks the sequence number and performs the corresponding operation on `k`. If the sequence number does not match any operation, it returns a default value of 1.

### isValidHash Function
The `isValidHash` function is used to check if a given hash has the required number of leading zeros. It iterates through the hash characters and checks if the number of leading zeros matches the required number. It returns `true` if the hash is valid, indicating that it meets the required leading zeros.



## The Scenario

To minimizing energy consumption associated with Proof-of-Work (PoW) systems, we have implemented a unique approach called the "Developer Mining Phase." This phase aims to significantly reduce energy usage while providing a rewarding opportunity for developers, founders, and contributors.

During the Developer Mining Phase, we introduce specific scenarios that allow developers to mine with reduced energy consumption. By allocating a portion of the total mining assets to developers, we ensure their valuable contributions are duly recognized and rewardeds.

The "Developer Mining Phase" not only reduces energy consumption in PoW systems but also provides a platform to appreciate the exceptional work done by developers, founders, and contributors. By incentivizing their efforts and introducing energy-efficient mining strategies, we create a sustainable and rewarding environment for all participants.


### Developer Mining Phase:

The condition for the developer mining phase is based on the `developerMining` variable, which is initially set to `false`. In the code, there are several scenarios mentioned that can trigger the developer mining phase. These scenarios are as follows:

a. Scenario 1: Developer mining a percentage of total assets with reduced difficulty - When `developerMining` is `true`, the mining assets for developers are calculated, and the difficulty is adjusted accordingly.

b. Scenario 2: Probability-based developer mining over a certain period - If the random number generated (`dis(gen) < miningProbability`) satisfies the probability condition, the `developerMining` variable is set to `true`, and the difficulty is adjusted accordingly.

### Actions during Developer Mining Phase:

While in the developer mining phase, the mining process continues within the `performMining()` function. The mining process involves performing mathematical operations on a variable `k`, adjusting the difficulty, and checking if the target hash is met.

If a successful mining result is obtained, the code performs the following actions:

a. Scenario 3: Automatically switching to the normal mining phase once developer mining is done - If `developerMining` is `true` and the `developerMiningAssets` is depleted (`developerMiningAssets <= 0`), the `developerMining` variable is set to `false`, and the difficulty is adjusted accordingly.

b. Outputting the successful mining result - The successful mining result is displayed on the console.

Conditions for Exiting the Mining Process:

The mining process continues in a loop until certain conditions are met:

a. If the target hash is met (`if (meetsDifficultyTarget(std::to_string(k), target))`), the loop is exited, and the successful mining result is outputted.

b. If a timeout duration is reached (`if (currentTime - startTime >= timeoutDuration)`), the mining process is terminated, and a timeout message is displayed.

In summary, the "developers mining phase" condition is based on the `developerMining` variable, which is triggered by certain scenarios and probability-based conditions. During the developer mining phase, the mining process continues with adjusted difficulty. Once the mining goals or conditions are met, the code can automatically switch to the normal mining phase or terminate the mining process based on the timeout duration.

### This repository is part of the  [SPHINXMiner](https://github.com/SPHINX-HUB-ORG/SPHINXMINER)

Please note that the code in this repository is a part of the SPHINXPoW algorithm, which is currently in development and not fully integrated or extensively tested for functionality. The purpose of this repository is to provide a framework and algorithm for the mining scheme in the SPHINX blockchain project.

As the project progresses, further updates and enhancements will be made to ensure the code's stability and reliability. We encourage contributors to participate in improving and refining the SPHINXPoW algorithm by submitting pull requests and providing valuable insights.

We appreciate your understanding and look forward to collaborative efforts in shaping the future of the SPHINX blockchain project.


# Getting Started
To get started with the SPHINX blockchain project, follow the instructions below:

1. Clone the repository: `git clone https://github.com/ChyKusuma/SPHINXPoW.git`
2. Install the necessary dependencies (List the dependencies or provide a link to the installation guide).
3. Explore the codebase to understand the project structure and components.
4. Run the project or make modifications as needed.


## Contributing
We welcome contributions from the developer community to enhance the SPHINX blockchain project. If you are interested in contributing, please follow the guidelines below:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix: `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/your-bug-fix`.
3. Make your modifications and ensure the code remains clean and readable.
4. Write tests to cover the changes you've made, if applicable.
5. Commit your changes: `git commit -m "Description of your changes"`.
6. Push the branch to your forked repository: `git push origin your-branch-name`.
7. Open a pull request against the main repository, describing your changes and the problem it solves.
8. Insert your information (i.e name, email) in the authors space.

## License
Specify the license under which the project is distributed (MIT License).

## Contact
If you have any questions, suggestions, or feedback regarding the SPHINX blockchain project, feel free to reach out to us at [sphinxfounders@gmail.com](mailto:sphinxfounders@gmail.com).
