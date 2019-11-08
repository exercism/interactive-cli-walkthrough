# Walkthrough

A repository for the text found in the Exercism CLI installation walkthrough.

To start contributing, please view the [Contributing Guide](https://github.com/exercism/interactive-cli-walkthrough/blob/master/CONTRIBUTING.md).

## Deploying changes to production

To get new changes to production we need to:

1. Compile
2. Copy the compiled file to the exercism/website-copy repository
3. Commit to master and push to GitHub

Ideally we wouldn't worry about submitting a pull request for this,
since the changes have been reviewed in a pull request in the
exercism/interactive-cli-walkthrough repository before compiling.  The
master branch on website-copy is protected, so you will need to create a
pull request.

```
rake compile:prod
cp compiled_prod.html ../website-copy/walkthrough/index.html
```

This can only be done by core website-copy contributors, who have push access on the
exercism/website-copy repository.
