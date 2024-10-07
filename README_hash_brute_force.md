
# Hash Generation & Collision Testing

This script generates random strings and tests for a specific hash pattern using the SHA-256 hashing algorithm. It demonstrates how brute force can be used to find an input that produces a hash with a desired prefix.

## Table of Contents
- [Overview](#overview)
- [How It Works](#how-it-works)
- [Functions](#functions)
- [Example Output](#example-output)
- [How to Run](#how-to-run)
- [Dependencies](#dependencies)

## Overview

This Python script generates random strings, appends them to a predefined challenge string, and then computes their SHA-256 hash. The goal is to find a string that, when hashed, produces a hash that starts with five zeros (`00000`).

The program continuously generates new random strings until it finds a match, at which point it outputs the corresponding hash and the time it took to find the match.

## How It Works

1. **String Generation**: Random strings are generated, consisting of lowercase and uppercase letters and digits.
2. **Hashing**: The generated string is appended to a challenge string and hashed using the SHA-256 algorithm.
3. **Checking the Hash**: The script checks whether the generated hash starts with the prefix `00000`. If it does, the solution is found.
4. **Time Measurement**: The time taken to find a solution is recorded and printed along with the hash.

### Variables:
- `challenge`: The predefined string (challenge) to which random strings are appended.
- `answer`: The randomly generated string that gets appended to the challenge.
- `solution`: The SHA-256 hash of the concatenated challenge and answer.
- `Found`: A flag used to control the brute force loop until a valid hash is found.

## Functions

### `generation(challenge = example_challenge, size = 24)`
This function generates a random string (`answer`) of a specified size, appends it to the challenge string, and returns the combined attempt and the random string.
- **Parameters**:
  - `challenge` (optional): The predefined string (default is `fgrt354ksnrte398kfjghqa42`).
  - `size` (optional): The size of the random string to generate (default is 24).
- **Returns**: A tuple containing the concatenated string (attempt) and the randomly generated answer.

### `testAttempt()`
This function performs the brute force search, continuously generating new attempts until a hash with the desired prefix is found. It records the time taken and prints the result.

## Example Output

```bash
00000d4fb93912ae5f7c2f4c54b32409ef45317a03f7e07dbf8dd203ec203305
timeTook:  13.456789 seconds
```

In the example above, the program found a hash that starts with `00000` after approximately 13.46 seconds.

## How to Run

1. **Install Python**: Ensure you have Python installed on your system.
2. **Run the Script**: Execute the script in a terminal or Python environment:

```bash
python hash_brute_force.py
```

The program will run until it finds a hash that starts with five zeros.

## Dependencies

- **Python 2.x or 3.x** (depending on the environment you run the code in).
- **hashlib**: This module is part of Python’s standard library for cryptographic hashing functions.
