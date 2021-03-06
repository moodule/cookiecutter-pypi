{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% for _ in cookiecutter.project_name %}={% endfor %}
{{ cookiecutter.project_name }}
{% for _ in cookiecutter.project_name %}={% endfor %}

{%- if is_open_source %}
.. image:: `pypi-shield`_
        :target: `pypi-target`_

.. image:: `readthedocs-shield`_
        :target: `readthedocs-target`_
        :alt: Documentation Status
{%- endif %}

{%- if cookiecutter.add_pyup_badge == 'y' %}
.. image:: `pyup-shield`_
     :target: `pyup-target`_
     :alt: Updates
{%- endif %}

{{ cookiecutter.project_short_description }}

{%- if is_open_source %}
* Free software: {{ cookiecutter.open_source_license }}
* Documentation: `readthedocs-target`_.
{%- endif %}

Table of Contents
-----------------

- `Table of Contents`_
- `Features`_
- `Development`_
- `Credits`_

Features
--------

* TODO

Development
-----------

Contributions welcome! Read the `contribution guidelines`_ first.

History
~~~~~~~

See the `history`_.

Community
~~~~~~~~~

See the `code of conduct`_.

Credits
-------

This package was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.

.. _`pypi-shield`: https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg
.. _`pypi-target`: https://pypi.python.org/pypi/{{ cookiecutter.project_slug }}
.. _`pyup-shield`: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg
.. _`pyup-target`: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
.. _`readthedocs-shield`: https://readthedocs.org/projects/{{ cookiecutter.project_slug | replace("_", "-") }}/badge/?version=latest
.. _`readthedocs-target`: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io/en/latest/

.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
.. _`code of conduct`: CODE_OF_CONDUCT.rst
.. _`contribution guidelines`: CONTRIBUTING.rst
.. _`Cookiecutter`: https://github.com/audreyr/cookiecutter
.. _`history`: HISTORY.rst
