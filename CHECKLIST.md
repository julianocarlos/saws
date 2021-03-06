Release Checklist
=================

A. Run unit tests

    $ tox

B. Run code checks

    $ scripts/run_code_checks.sh

C. Run manual smoke tests on Mac, Ubuntu, Windows*

D. Update and review `README.rst` and `Sphinx` docs

    $ scripts/update_docs.sh

E. Push changes

F. Review Travis, Codecov, and Gemnasium

G. Start a new release branch

    $ git flow release start x.y.z

H. Increment the version number in `saws/__init__.py`

I. Update and review `CHANGELOG`

    $ scripts/create_changelog.sh

J. Commit the changes

K. Finish the release branch

    $ git flow release finish 'x.y.z'

L. Input a tag

    $ vx.y.z

M. Push tagged release to develop and master

N. Temporarily remove README before pushing to PyPi  # TODO

O. Register package with PyPi

    $ python setup.py register -r pypi

P. Upload to PyPi

    $ python setup.py sdist upload -r pypi

Q. Upload Sphinx docs to PyPi

    $ python setup.py upload_sphinx

R. Review newly released package from PyPi

S. Install and run manual smoke tests on Mac, Ubuntu, Windows*

T. Restore README  # TODO

U. Rebuild Readthedocs at https://readthedocs.org/projects/saws/builds/

## Smoke Tests

Run the following on Python 2.7 and Python 3.4:

* Craete a new `virtualenv`
* Pip install `SAWS` into new `virtualenv`
* Run `SAWS`
* Empty cache
* Check resource load from cache
* Force refresh of resources
* Toggle toolbar options
* Verify toolbar options are saved across sessions
* Commands
    * Blank
    * aws
    * aws elb
    * aws s3api get-bucket-acl --bucket
    * aws ec2 describe-instances --instance-ids
    * aws ecls
    * aws ectagk
    * aws ectagv
    * aws ecstate
    * aws s3 ls s3:
    * aws s3 ls docs
* Run specialized tests based on code changes
