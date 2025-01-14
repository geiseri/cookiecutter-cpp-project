This TODO list is automatically generated from the cookiecutter-cpp-project template.
The following tasks need to be done to get a fully working project:

{% if cookiecutter.remote_url == 'None' -%}
* Set up a remote repository. You can e.g. create a project in GitHub or GitLab and run
  the following commands in your locally generated project folder: `git remote add origin <Remote-URL>`
  For a seamless integration, the name of the project should also be `{{ cookiecutter.project_slug }}`.
{%- else %}
* Push to your remote repository for the first time by doing `git push origin main`.
{%- endif %}
* Make sure that the following software is installed on your computer:
  * A C++-{{ cookiecutter.cxx_minimum_standard}}-compliant C++ compiler
  * CMake `>= 3.9`
{%- if cookiecutter.use_submodules == "No" %}
  * The testing framework [Catch2](https://github.com/catchorg/Catch2)
{%- if cookiecutter.python_bindings == "Yes" -%}
  * The [PyBind11](https://github.com/pybind/pybind11) library
{%- endif %}
{%- endif %}
{%- if cookiecutter.gitlab_ci == "Yes" %}
* Make sure that CI/CD pipelines are enabled in your Gitlab project settings and that
  there is a suitable Runner available. If you are using the cloud-hosted gitlab.com,
  this should already be taken care of.
{%- endif %}
{%- if cookiecutter.readthedocs == "Yes" %}
* Enable the integration of Readthedocs with your Git hoster. In the case of Github, this means
  that you need to login at [Read the Docs](https://readthedocs.org) and click the button
  *Import a Project*.
{%- endif %}
{%- if cookiecutter.doxygen == "Yes" %}
* Make sure that doxygen is installed on your system, e.g. by doing `sudo apt install doxygen`
  on Debian or Ubuntu.
{%- endif %}
{%- if cookiecutter.python_bindings == "Yes" %}
* Edit the parameters of `setup()` in `setup.py` file to contain the necessary information
  about your project, such as your email adress, PyPI classifiers and a short project description.
{%- endif %}
{%- if cookiecutter.pypi_release == "Yes" %}
* Add the secret variables `TESTPYPI_API_TOKEN` and `PYPI_API_TOKEN` to your GitHub project.
  These variables can be generated by heading to `https://test.pypi.org/` and `https://pypi.org`,
  adding a new project and generating these tokens.
{%- endif %}
{%- if cookiecutter.codecovio == "Yes" %}
* Enable the integration with `codecov.io` by heading to the [Codecov.io Website](https://codecov.io),
  log in (e.g. with your Github credentials) and enable integration for your repository. This will
  allow you to have automatic coverage reports on pull requests, but is not necessary to display
  the coverage badge in the README.
{%- endif %}
{%- if cookiecutter.sonarcloud == "Yes" %}
* Enable the integration with `sonarcloud.io` by heading to the [Sonarcloud.io Website](https://sonarcloud.io),
  log in (e.g. with your Github credentials), add the repository and select *Github Actions* as the
  preferred method of integration. Follow step 1 and set up the secret variable `SONAR_TOKEN`. Step 2
  and 3 are already taken care of by this cookiecutter. In order to have the SonarCloud badge in the
  README show something meaningful, a *New Code Definition* needs to be configured in Sonarcloud under
  *Administration/New Code*.
{%- endif %}