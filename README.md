# Publish Python package seed-vc with the Python Package Index

## Prepare:
Initializing and updating submodules

git submodule update --init --recursive

## Clean:
Clean the dist/ directory

rm -rf dist

## Build:
Build sdist and wheel for seed_vc only

python3 -m pip install -U build twine

python3 -m build

This creates:

dist/seed_vc-0.1.0-py3-none-any.whl

dist/seed_vc-0.1.0.tar.gz

## Test install: 
python -m venv .venv && .venv/bin/pip install dist/seed_vc-0.1.0-*.whl

## Upload:
Upload only your package files (not all files in dist)

python3 -m twine upload dist/seed_vc-0.1.0*

Tip: For a dry run against TestPyPI first:

python3 -m twine upload --repository testpypi dist/seed_vc-0.1.0*