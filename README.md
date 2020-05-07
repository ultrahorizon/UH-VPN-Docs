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

## Building the docs locally

- Clone the repo:

```bash
$> git clone git@github.com:ultrahorizon/UH-VPN-Docs.git
```

- Install a Python 3.7 virtualenv inside the root of the repository folder:

```bash
$> virtualenv --python=python3.7 .
```

- Install Python dependencies:

```bash
$> pip install -r requirements.txt
```

- Build the docs and view the output in the generated `build` directory:

```bash
$> make html
```

