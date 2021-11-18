# s-expression for EO product band math


## Development 

```bash
cd app-s-expression
```

Create the Python environment with `mamba` (faster) or `conda` (slower):

```bash
mamba env create -f environment.yml
```

Activate the Python environment with:

```bash
conda activate env_app_snuggs
```

### Build the Python project

To build and install the project locally:

```
python setup.py install
```

Test the CLI with:

```bash
s-expression --help
```

That returns:

```console
$ s-expression --help
Usage: s-expression [OPTIONS]

  Applies s expressions to EO acquisitions

Options:
  -i, --input_reference PATH  Input product reference  [required]
  -s, --s-expression TEXT     s expression  [required]
  -b, --cbn TEXT              Common band name  [required]
  --help                      Show this message and exit.
```

### Build the container

```console
docker build . -t snuggs
```

### Execution

```console
cwltool --parallel app-package.cwl#s-expression params.yml
```

## Releases

Releases are published in https://github.com/EOEPCA/app-snuggs/releases

