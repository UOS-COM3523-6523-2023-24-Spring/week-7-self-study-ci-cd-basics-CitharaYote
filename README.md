# Self study for Week 7 (CI/CD Basics)

## Install

```bash
python -m pip install pytest
```

## Task 1

Run the following on the pycharm built-in terminal:

```bash
pytest -v
```

You can see that `test_simple_function2` is failed. Fix the code (line 2 in `main.py`) to make the test case pass.

When it's fixed, push the change to GitHub to see the GitHub Actions in action.

## Task 2

If you uncomment `test_complex_function` in `test_main.py`, you can see that the test case is most likely failed.
This is because the behaviour of `complex_function` is non-deterministic (depending on `random_function`).

Such non-deterministic behaviour is not uncommon in real-world software system.
How can we test such non-deterministic behaviour? Think about this. (No need to implement anything)

### Ideas

- Replace the non-deterministic part of the code with a 'mock' object that returns a deterministic value for testing.
- Use a set seed to ensure that the random function returns the same value every time it is called during the tests.
- If the non-deterministic code is mostly random (as opposed to I/O or network calls), a statistical model could be used to check the results lie in the distribution expected over a large number of runs.
