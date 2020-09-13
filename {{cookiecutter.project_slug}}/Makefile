.PHONY: clean clean-build clean-docs clean-pyc clean-test docs help
.DEFAULT_GOAL := help
ENVIRONMENT := poetry run

help:
	@echo "clean............remove all build, test, coverage and Python artifacts"
	@echo "clean-build......remove build artifacts"
	@echo "clean-docs.......remove documentation building artifacts"
	@echo "clean-pyc........remove Python file artifacts"
	@echo "clean-test.......remove test and coverage artifacts"
	@echo "docs.............build the documentation"
	@echo "help.............show this help message"
	@echo "init.............install the dependencies in a local environment"
	@echo "lint.............check code style agains the PEP"
	@echo "release..........publish the package on pypi"
	@echo "test.............run tests quickly with the default Python"

clean: clean-build clean-docs clean-pyc clean-test ## remove all build, test, coverage and Python artifacts

clean-build: ## remove build artifacts
	rm -fr build/
	rm -fr dist/
	rm -fr .eggs/
	find . -name '*.egg-info' -exec rm -fr {} +
	find . -name '*.egg' -exec rm -f {} +

clean-docs: ## remove the documentation building artifacts
	rm -f docs/{{ cookiecutter.project_slug }}.rst
	rm -f docs/modules.rst

clean-pyc: ## remove Python file artifacts
	find . -name '*.pyc' -exec rm -f {} +
	find . -name '*.pyo' -exec rm -f {} +
	find . -name '*~' -exec rm -f {} +
	find . -name '__pycache__' -exec rm -fr {} +

clean-test: ## remove test and coverage artifacts
	rm -f .coverage
	rm -fr htmlcov/

coverage: ## check code coverage quickly with the default Python
	$(ENVIRONMENT) coverage run --source {{ cookiecutter.project_slug }} setup.py test
	$(ENVIRONMENT) coverage report -m
	$(ENVIRONMENT) coverage html

docs: clean-docs ## generate Sphinx HTML documentation, including API docs
	$(ENVIRONMENT) sphinx-apidoc -o docs/ {{ cookiecutter.project_slug }}
	$(MAKE) -C docs clean
	$(MAKE) -C docs html

init: clean ## install the package to the active Python's site-packages
	poetry install

lint: ## check style with flake8
	$(ENVIRONMENT) flake8 {{ cookiecutter.project_slug }} tests

release: ## package and upload a release
	poetry build
	poetry publish

test: ## run tests quickly with the default Python
	$(ENVIRONMENT) python -m unittest
