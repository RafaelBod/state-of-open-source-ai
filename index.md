# State of Open Source AI Book - 2023 Edition

Site: {{ baseurl }}

*Clarity in the current fast-paced mess of Open Source innovation.*

As a data scientist/developer with a 9 to 5 job, it's difficult to keep track of all the innovations. There's been enormous progress in the field in the last year.

The guide covers all the most important categories in the Open Source AI space, from model evaluations to deployment. It includes a [](glossary) for you to quickly check definitions of new frameworks & tools.

A quick TL;DR overview is included at the top of each section. We outline the pros/cons and general context/background for each topic. Then we dive a bit deeper. Examples include data models were trained on, and deployment implementations.

## Who is This Guide For?

```{admonition} Prerequisites to Reading
:class: warning
You should already know the basic principles of MLOps {cite}`google-mlops,redhat-mlops,ml-ops`, i.e. you should know that the traditional steps are:

1. Data engineering (preprocessing, curation, labelling, sanitisation)
2. Model engineering (training, architecture design)
3. Automated testing (CI)
4. Deployment/Automated Inference (CD)
5. Monitoring (logging, feedback, drift detection)
```

You haven't followed the most recent developments in open source AI over the last year, and want to catch up quickly.
We go beyond just mentioning the models, but also include things such as changing infrastructure, licence pitfalls, and novel applications.

(toc)=

## Table of Contents

We identified the main categories for what concerns open-source tooling, models, and MLOps and we framed the landscape into the following table.

Chapter | Examples
---|---
[](licences) | LLaMA, HuggingFace, Apache-2.0
[](eval-datasets) | OpenLLM Leaderboard, Datasets
[](models) | LLaMA 1 vs 2, Falcon, Stable Diffusion, DALL-E
[](uncensored-models) | FraudGPT, PoisonGPT
[](fine-tuning) | h20, ...
[](model-formats) | ONNX, Apache TVM, GGML
[](mlops-engines) | BentoML, llama.cpp, ray
[](vector-stores) | weaviate, qdrant, milvus, redis, chroma
[](sdk) | langchain, haystack, llama index
[](desktop-apps) | LMStudio, GPT4All UI
[](hardware) | NVIDIA GPUs, Mac, iPhone

## Contributing

We understand that the current open source ecosystem is moving at light-speed. This source of this guide is available on GitHub at {{ repo_url }}. Please do [create issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue) or [open pull requests](https://docs.github.com/en/get-started/quickstart/contributing-to-projects) with any feedback or contributions you may have.

### Editing the Book

- Using [GitHub Codespaces](https://codespaces.new/premAI-io/state-of-open-source-ai), you can edit code & preview the site in your browser without installing anything.
- Alternatively, to run locally, open {{ '[this repository](' + repo_url + ')' }} in a [Dev Container](https://containers.dev) (most likely [using VSCode](https://code.visualstudio.com/docs/devcontainers/containers#_installation)).
- Or instead, manually set up your own Python environment:

  ```sh
  pip install -r requirements.txt                # setup
  jupyter-book build --builder dirhtml --all .   # build
  python -m http.server -d _build/dirhtml        # serve
  ```

  ````{admonition} alternative: live rebuilding & serving (experimental)
  :class: tip, dropdown
  ```sh
  pip install -r requirements.txt sphinx-autobuild # setup
  jupyter-book config sphinx .                     # config
  sphinx-autobuild -b dirhtml . _build/dirhtml     # build-serve
  ```
  ````

(index#formatting)=

### Formatting

````{note}
```{eval-rst}
Don't worry about making it perfect, it's fine to open a (`draft <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests#draft-pull-requests>`_) PR and `allow edits from maintainers <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork>`_ to fix it |:heart:|
```
````

- [Quickstart](https://jupyterbook.org/en/stable/reference/cheatsheet.html)
- [Full reference](https://jupyterbook.org/en/stable/content/myst.html)
- Create a new chapter:
  + create `some-file.md` (containing `# Some File` heading and `{{ comments }}` footer)
  + add `- file: some-file` to `_toc.yml`
  + add `[](some-file) | summary` to [ToC](toc)
- Figures:

  ```{figure-md} fig-ref
  :class: margin-caption
  ![alt-text](https://static.premai.io/logo.png){width=200px align=left}

  This is a **figure caption** *in the margin*, vis [jupyterbook#markdown-figures](https://jupyterbook.org/en/stable/content/figures.html#markdown-figures)
  ```

  + [inline ref](fig-ref)
  + numbered ref: {numref}`fig-ref`
  + custom ref: {numref}`Figure {number} with caption "{name}" <fig-ref>`
  + please use https://github.com/premAI-io/static.premai.io to host images & data

- [](glossary) term: {term}`GPU`
  + custom inline text: {term}`GPUs <GPU>`
- [BibTeX](https://jupyterbook.org/en/stable/tutorials/references.html#add-your-references) `references.bib` citation: {cite}`python`

% comment lines (not rendered) are prefixed with a "%"

### Contributors

{{ '[![](https://contrib.rocks/image?repo=' + '/'.join(repo_url.split('/')[-2:]) + ')](' + repo_url + '/graphs/contributors)' }}

## Conclusion

Open Source AI represents the future of privacy and ownership of data. On the other hand, in order to make this happen a lot of innovation should come into place. In the last year, already the open-source community demonstrated how motivated they are in order to deliver quality models to the hands of consumers creating already few big innovations in different AI fields. At the same time, this is just the beginning. Many improvements in multiple directions must be made in order to compare the results with centralized solutions.

At Prem we are on a journey to make this possible, with a focus on developer experience and deployment for any sort of developers, from Web Developers with zero knowledge about AI to affirmed Data Scientist who wants to quickly deploy and try these new models and technologies in their existing infra without compromising privacy.

## Join our Community

- Ask for support on [our Discord server](https://discord.com/invite/kpKk6vYVAn).
- To keep up-to-date, [follow us on Twitter](https://twitter.com/premai_io).
- Report bugs or request features at https://github.com/premAI-io/prem-app.

(glossary)=

## Glossary

%TODO: define all these & use them where appropriate

```{glossary}
:sorted:
Foundation model
Evaluation
Auto-regressive language model
Decoder-style transformer
Tokens
[GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit)
  Graphics Processing Unit: hardware originally designed to accelerate computer image processing, but now often repurposed for [embarrassingly parallel](https://en.wikipedia.org/wiki/Embarrassingly_parallel) computational tasks in machine learning.

A100, V100, H100
Vector
Embedding
Vector Embeddings
Vector Store
Vector Database
supervised fine-tuning
Diffusion-based text-to-image generative mode
VRAM
```