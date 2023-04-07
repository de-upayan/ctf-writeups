## Flag
```
GREP{5388110365956729}
```

## Problem Statement

Your card got lost while eating at the ANC. You have written it somewhere, but the two digits are unclear.

FLAG FORMAT: `GREP{card number}`

## Files

*Credit Card .jpg*

<img src="https://user-images.githubusercontent.com/96875426/230577302-270b89c2-22b3-4f32-adf4-bf12204defc3.jpeg" width="500">

## My solution

From the picture, we inferred that the card number was of the form `538XX10365956729`, since Credit Card numbers are usually 16-digit long. Also, I knew that the [**Luhn Algorithm**](https://en.wikipedia.org/wiki/Luhn_algorithm) was used to verify the validity of a Credit Card number.

Writing a script to generate all possible Card numbers using the [luhn-validator](https://pypi.org/project/luhn-validator/) package gave me the following:

```python

## author: twoplusthree

from luhn_validator import validate

for i in range(10):
    for j in range(10):
        cnd = f"538{i}{j}10365956729"

        if validate(cnd):
            print(cnd)

```

```console

upayan@CTF$ python3.8 main.py
5380010365956729
5381910365956729
5382410365956729
5383810365956729
5384310365956729
5385710365956729
5386210365956729
5387610365956729
5388110365956729
5389510365956729

```

Trying out all of the 10 possible combinations solved the question.
