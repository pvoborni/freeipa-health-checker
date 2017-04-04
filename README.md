# freeipa-health-checker

[![Build Status](https://travis-ci.org/felipevolpone/freeipa-health-checker.svg?branch=master)](https://travis-ci.org/felipevolpone/freeipa-health-checker)
![Python Version](https://img.shields.io/badge/python-2.7-green.svg)
![Python Version](https://img.shields.io/badge/python-3.5-green.svg)

### What is the purpose of this tool
The main goal of this tool is to provide verifications that can be done on a [FreeIPA](http://freeipa.org) or [Dogtag](http://pki.fedoraproject.org) environment; in order to help the users of these projects to have a feedback if some parts of the installation were done correctly.

### Main features until now
* List certificates
* Check if the certificates expired
* Check if the certificates are on the right path, if they have the expected
trust flags and check if certmonger is monitoring the certs.

### How to use it
1. Clone the project
```bash
git clone git@github.com:felipevolpone/ipa-health-checker.git
cd ipa-health-checker;
```

2. Install [certutil](https://fedoraproject.org/wiki/NSS_Tools_:_certutil)
```bash
apt-get install libnss3-tools
yum install libnss3-tools
```

3. Start using it:
```bash
python -m ipa_health_checker.checker -h
python -m ipa_health_checker.checker ck_kra_setup [--dir <path>] [--cert <path>]
python -m ipa_health_checker.checker ck_path_and_flags [--csv_file <path>]
python -m ipa_health_checker.checker list_certs <path>
python -m ipa_health_checker.checker certs_expired <path>
```

### Testing it
It is relevant to say that the unit tests do not use any mock. So, it's
necessary to have the certutil command installed on the machine. Check the
`How to use it` section.

How to run the tests:
```bash
python -m unittest discover tests -p '*.py'  # or use python3
```

## Next steps
Please check the [issues](https://github.com/felipevolpone/freeipa-health-checker/issues)
