# Contributing

Contributions are welcome, and they are greatly appreciated! Every little bit helps, and credit will always be given.

You can contribute in many ways:

## Types of Contributions

### Report Bugs

Report bugs at <https://github.com/elgertam/cookiecutter-pipenv/issues>

If you are reporting a bug, please include:

- Your operating system name and version.
- Any details about your local setup that might be helpful in troubleshooting.
- Detailed steps to reproduce the bug.

### Fix Bugs

Look through the GitHub issues for bugs. Anything tagged with \"bug\" and \"help wanted\" is open to whoever wants to implement a fix for it.

### Implement Features

Look through the GitHub issues for features. Anything tagged with \"enhancement\" and \"help wanted\" is open to whoever wants to implement it.

### Write Documentation

Cookiecutter PyPackage could always use more documentation, whether as part of the official docs, in docstrings, or even on the web in blog posts, articles, and such.

### Submit Feedback

The best way to send feedback is to file an issue at <https://github.com/elgertam/cookiecutter-pipenv/issues>.

If you are proposing a new feature:

- Explain in detail how it would work.
- Keep the scope as narrow as possible, to make it easier to implement.
- Remember that this is a volunteer-driven project, and that contributions are welcome :)

## Get Started

Ready to contribute? Here\'s how to set up `cookiecutter-pipenv` for local development. Please note this documentation assumes you already have `Pipenv` and `git` installed and ready to go.

1. Fork the [cookiecutter-pipenv](https://github.com/elgertam/cookiecutter-pipenv) repo on GitHub.

2. Clone your fork locally:

    ```bash
    cd path_for_the_repo
    git clone git@github.com:YOUR_NAME/cookiecutter-pipenv.git
    ```

3. Assuming you have `Pipenv` installed, you can create a new environment for your local development by typing:

    ```bash
    pipenv install
    ```

4. Create a branch for local development:

    ```bash
    git checkout -b name-of-your-bugfix-or-feature
    ```

5. When you\'re done making changes, check that your changes pass flake8. Since, this package contains mostly templates the flake should be run for tests directory:

    ```bash
    flake8 ./tests
    ```

6. The next step would be to run the test cases. `cookiecutter-pypackage` uses py.test, you can run PyTest. Before you run pytest you should ensure all dependancies are installed:

    ```bash
    pipenv install --dev
    py.test ./tests
    ```

    If you get any errors while installing cryptography package (something like `#include <openssl/aes.h>`). Please update your pip version and try again:

    ```bash
    # Update pip
    $ pip install -U pip
    ```

7. Before raising a pull request you should also run tox. This will run the tests across different versions of Python:

    ```bash
    tox
    ```

    > If you are missing flake8, pytest and/or tox, just pip install them into your virtualenv.

8. If your contribution is a bug fix or new feature, you may want to
    add a test to the existing test suite. See section Add a New Test
    below for details.

9. Commit your changes and push your branch to GitHub:

    ```bash
    git add .
    git commit -m "Your detailed description of your changes."
    git push origin name-of-your-bugfix-or-feature
    ```

10. Submit a pull request through the GitHub website.

## Pull Request Guidelines

Before you submit a pull request, check that it meets these guidelines:

1. The pull request should include tests.
2. If the pull request adds functionality, the docs should be updated. Put your new functionality into a function with a docstring, and add the feature to the list in README.rst.
3. The pull request should work for Python 2.7, 3.4, 3.5 and 3.6, and for PyPy. Check <https://travis-ci.org/elgertam/cookiecutter-pipenv/pull_requests> and make sure that the tests pass for all supported Python versions.

## Add a New Test

When fixing a bug or adding features, it\'s good practice to add a test to demonstrate your fix or new feature behaves as expected. These tests should focus on one tiny bit of functionality and prove changes are correct.

To write and run your new test, follow these steps:

1. Add the new test to [tests/test\_bake\_project.py](https://github.com/elgertam/cookiecutter-pipenv/blob/master/tests/test_bake_project.py). Focus your test on the specific bug or a small part of the new feature.

2. If you have already made changes to the code, stash your changes and confirm all your changes were stashed:

    ```bash
    git stash
    git stash list
    ```

3. Run your test and confirm that your test fails. If your test does not fail, rewrite the test until it fails on the original code:

    ```bash
    py.test ./tests
    ```

4. Run the tests with tox to ensure that the code changes work with different Python versions:

    ```bash
    tox
    ```

5. Proceed work on your bug fix or new feature or restore your changes. To restore your stashed changes and confirm their restoration:

    ```bash
    git stash pop
    git stash list
    ```

6. Rerun your test and confirm that your test passes. If it passes, congratulations!