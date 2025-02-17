# Project

**Note: this tool is a work in progress and not yet in a useful state**

This project is an open source tool to convert TIMES model Excel input files to DD format ready for processing by [GAMS](https://www.gams.com/).  The intention is to make it easier for people to reproduce research results on TIMES models.

[TIMES](https://iea-etsap.org/index.php/etsap-tools/model-generators/times) is an energy systems model generator from the International Energy Agency that is used around the world to inform energy policy.
It is fully explained in the [TIMES Model Documentation](https://iea-etsap.org/index.php/documentation).

The Excel input format accepted by this tool is documented in the [TIMES Model Documentation PART IV](https://iea-etsap.org/docs/Documentation_for_the_TIMES_Model-Part-IV.pdf).  Additional table types are documented in the [VEDA support forum](https://forum.kanors-emr.org/printthread.php?tid=140).  Example inputs are available at https://github.com/kanors-emr/Model_Demo_Adv_Veda

## Installation and Basic Usage

The tool is not (yet) on PyPI, but you can still install it using pip (preferably in a virtual environment) by cloning the repository and running the following command in the root directory:
```bash
pip install .
```

After installation, run the following command to see the basic usage and available options:
```bash
times-excel-reader --help
```

## Development Setup

We recommend installing the tool in editable mode (`-e`) in a Python virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install -r requirements.txt
pip install -e .[dev]
```

We use the [black](https://pypi.org/project/black/) code formatter. The `pip` command above will install it along with other requirements.

We also use the [pyright](https://github.com/microsoft/pyright/) type checker -- our GitHub Actions check will fail if pyright detects any type errors in your code. You can install pyright in your virtual environment and check your code by running these commands in the root of the repository:
```bash
pip install pyright==1.1.304
pyright
```
Additionally, you can install a git pre-commit that will ensure that your changes are formatted and pyright detects no issues before creating new commits:
```bash
pre-commit install
```

## Running Benchmarks

See our GitHub Actions CI `.github/workflows/ci.yml` and the utility script `utils/run_benchmarks.py` to see how to run the tool on the DemoS models.

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft
trademarks or logos is subject to and must follow
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
