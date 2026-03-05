# Contributing to AutoEmulate


💫⚙️🤖 We're excited that you're here and want to contribute. 🤖⚙️💫


We want to ensure that every user and contributor feels welcome, included and supported to participate in the AutoEmulate community. Whether you're a seasoned developer, a machine learning researcher, a data scientist, or just someone eager to learn and contribute, **you are welcome here**. We value every contribution, be it big or small, and we appreciate the unique perspectives you bring to the project.


We hope that the information provided in this document will make it as easy as possible for you to get involved. If you find that you have questions that are not discussed below, please let us know through one of the many ways to [get in touch](#get-in-touch).


## Important Resources


If you'd like to find out more about AutoEmulate, make sure to check out:


1. **README**: For a high-level overview of the project, please refer to our [README](https://github.com/alan-turing-institute/autoemulate/blob/main/README.md).
2. **Documentation**: For more detailed information about the project, please refer to our [documentation](https://alan-turing-institute.github.io/autoemulate).


## How to Contribute


This section provides a high-level guide to contributing to AutoEmulate, designed for those with little or no experience with open source projects. For more detailed information, please also refer to the docs for:


* [contributing emulators](https://alan-turing-institute.github.io/autoemulate/community/contributing-emulators.html)
* [contributing to the docs](https://alan-turing-institute.github.io/autoemulate/community/contributing-docs.html)


We welcome contributions of all kinds, be it code, documentation, or community engagement. We encourage you to read through the following sections to learn more about how you can contribute to the package.


## Use of AI Tools


AI tools can be helpful during development, but all contributors remain fully responsible for the quality, correctness, and originality of what they submit.

When using AI tools, please follow these rules:

- Do not submit code or documentation you do not understand.
- Verify generated output by running tests and checking references.
- Do not paste confidential, sensitive, or proprietary data into external AI tools.
- Ensure generated content is compatible with this repository's licensing and attribution requirements.
- If AI assistance materially shaped a pull request, briefly disclose how it was used in the PR description.

Maintainers may ask for clarification, additional tests, or a rewrite if AI-generated content is incorrect, unverifiable, or does not meet project quality standards.

## Development guide


### Running the test-suite on Apple silicon (M-series)


PyTorch’s Metal (MPS) backend still lacks some `float64` linear-algebra ops (e.g. `linalg_cholesky_ex`, `linalg_eigh`). On an M-series Mac these ops fail three Gaussian-process tests unless you let PyTorch fall back to CPU.


```# one-line fix: fall back to CPU for unsupported MPS ops
export PYTORCH_ENABLE_MPS_FALLBACK=1
pytest -q        # 831 passed, warnings only
```
If you prefer to skip the affected tests instead:


```
pytest -k "not mps"
```


## How to Submit Changes


We follow the same instructions for submitting changes to the project as those developed by [The Turing Way](https://github.com/the-turing-way/the-turing-way/blob/main/CONTRIBUTING.md#making-a-change-with-a-pull-request). In short, there are five steps to adding changes to this repository:
