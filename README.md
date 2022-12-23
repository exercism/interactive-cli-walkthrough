# Walkthrough

A repository for the text found in the Exercism CLI installation walkthrough.

To start contributing, please view the [Contributing Guide](https://github.com/exercism/interactive-cli-walkthrough/blob/main/CONTRIBUTING.md).

## Deploying changes to production

To get new changes to production we need to:

1. Compile
2. Copy the compiled file to the [exercism/website-copy](https://github.com/exercism/website-copy) repository
3. Commit to `main` and push to GitHub

We don't worry about submitting a pull request for this, since the changes have
been reviewed in a pull request in the exercism/interactive-cli-walkthrough repository
before compiling.

```shell
rake compile:prod
cp compiled_prod.html ../website-copy/walkthrough/index.html
```

This can only be done by core website-copy contributors, who have push access on the
exercism/website-copy repository.
