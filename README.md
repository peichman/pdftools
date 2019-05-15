# pdftools

Tools for making PDFs out of PDFs.

## pdfbooklet

```
pdfbooklet input.pdf > output.pdf
```

Rearrange and rotate pages so that when printed 2-up or 4-up duplex, they can be
folded and cut into signatures for binding.

Defaults to 8 page booklets (4-up printing). Specify `4` as the second argument
for 4 page (2-up) booklets:

```
pdfbooklet input.pdf 4 > output.pdf
```

## pdfcombine

```
pdfcombine input1.pdf input2.pdf [...] > output.pdf
```

Combine multiple PDF files into a single PDF file.

## pdfmerge

```
pdfmerge description.yml > output.pdf
```

Extract pages in an arbitrary order from multiple PDF files, and assemble them
into a new PDF file. The instructions for doing this are given in a YAML file:

```
base_dir: /home/peter/documents
file_pattern: %s
page_map:
    - [ 'file1.pdf', [1,4,5]]
    - [ 'file2.pdf', [9,1,3,6]]
    # etc.
```
