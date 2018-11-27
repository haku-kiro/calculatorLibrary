# calculatorLibrary
Tests for setting up a CI pipeline using circleci 

## File location explained

- The venv is located in the calcEnv (Note to future self, add to gitignore, or name env which is contained in default .gitignore)
- The logic is found in the calculator.py file.
- Unit tests are found in the test_calculator.py file.

## Replicate

- To replicate, first create a virtualenv (Best practise)
- Install the requirements file:

```python

# Run when you env is active
pip install -r /path/requirements.txt

```

## Checks

- To check that the file conforms to pep8, will be using flake8.
  - To check, run: flake8 <filename>.py --statistics
  - Note, if you want to run against all files, omit the filename. I didn't do this as I have a virtualenv, takes longer.
  - If flake8 returns nothing the linting has passed.
- To check that the code is running we'll be using pytest and write our own unit tests.
  - Our tests will be found in the test_calculator.py file.
  - Once we have written our simple tests, we can run the following:
    - pytest -v --cov
    - This is where the coverage module that we installed comes in, it shows us how much of our application is being tested (well the individual file)
    - As a side note, pytest finds the tests by looking for py files prefixed with things like 'test_'

## CircleCI

To use circle ci, you repo is expected to contain a .circleci folder with a config.yml file inside that specifies all the build requirements of your application.

- Created a circleci folder
  - Have a config.yml file with build specs