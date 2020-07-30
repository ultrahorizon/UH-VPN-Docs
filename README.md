# UH VPN Docs
Open-source issue tracker and documentation hub for [UH VPN](https://uh-vpn.com).

[![Documentation Status](https://readthedocs.org/projects/uh-vpn/badge/?version=latest)](https://uh-vpn.readthedocs.io/en/latest/?badge=latest)

#### This repository aims to accomplish four main tasks:

1. Provide a thorough documentation platform to aid the use of UH VPN.
2. Provide the ability for users to ask questions directly to UH VPN developers and the wider community.
3. Provide the ability for users to submit bug reports directly to UH VPN developers.
4. Provide the ability for users to suggest new features and to up-vote already suggested features for consideration in future updates to the service.

## Submitting a question / bug / request:

Head over to [issues](https://github.com/ultrahorizon/UH-VPN-Docs/issues/new/choose) and create a new one by using one of the pre-made templates to describe your question/bug/request.
Our development team aim to respond within two days.

### Issue tags:

We track issues using multiple tags and each one has a specific meaning in relation to an issue you file and it's important you understand what each one means so that you can understand how your issue is being handled. Please see this [list](https://github.com/ultrahorizon/UH-VPN-Docs/labels) for descriptions of all of our tags.

## Contributions

To contribute to UH VPN Docs, please do the following:

1. Create an issue in UH VPN Docs and assign yourself to it.
2. Fork this repo.
3. Make your changes on a feature branch within your newly forked repository.
4. Create a pull request within this repository proposing a merge from your personal feature branch into the master branch in this repository.
5. Link the issue from the pull request by including the text `Resolves #num` where `num` is the appropriate issue number.
6. Request a review from a moderator.

## Building the docs locally

- Clone the repo:

```bash
git clone git@github.com:ultrahorizon/UH-VPN-Docs.git
```

- Install a Python 3.7 virtualenv inside the root of the repository folder:

```bash
virtualenv --python=python3.7 .
```

- Install Python dependencies:

```bash
pip install -r requirements.txt
```

- Build the docs and view the output in the generated `build` directory:

```bash
make html
```
