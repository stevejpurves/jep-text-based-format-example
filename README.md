# JEP Text Based Notebook Format Example

This repo contains a minimal example of a Juptyer notebook in `.ipynb` format:

- [example.ipynb](example.ipynb)
- and [example.ipynb.json](example.ipynb) for easy viewing of the source

Alongside the same notebook in a the proposed new text based format: [example.md](/example.md)

More details on the proposal an be found [in the hackmd working document](https://hackmd.io/CmAhY_3tRK6ge4tqANflTg?view) and on the [Jupyter Enhancement Proposal repository](https://github.com/jupyter/enhancement_proposals)

## Questions

- should cell id's be kept consistently when present? even in markdown, thematic breasks will have to be for successful roundtrips to clients
- where whould top level fields on outputs go? in the working doc they are currently in yaml, but thisis in consistent, tried to be consistent in this example
- we should include the `metadata:` top level fields in cell metadata, or as we ok with metadata being unpacked into yaml and other top level field in the first line?
- we shoud relax out constrain on additional whitespace & newlines? in writing the `example.md` file here my text editor aggressively inserted whitespace on each save, as per it's normal markdown formatting.... this could be very inconvient fpor users if we are strict on whitespace between cells, cells and outputs etc...
