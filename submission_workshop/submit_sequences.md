# Submitting Sequences

Submission of genomes/consensus sequences can only be achieved through Webin-CLI.

## Webin-CLI

As with read submission, submission of sequences through the Webin-CLI utility requires manifest files providing information about the data files. Using the `-context genome` we usually provide metadata about how the sequence was generated and from which platforms the underlying data originated. 

In the `sequences/webin-cli` directory, we provide all example files required to submit sequences against our 3 samples.
```bash
cd $WORKSHOP/sequences/webin-cli
ls
```

For each of our 3 samples, you will find:
1. a `*_manifest.txt` file defining information about the sequence, including the name of the fasta file containing the sequence 
2. a `*.fasta.gz` file : a fasta file containing the sequence data. This file must be compressed for submission
3. a `*_chrm_list.txt.gz` file : defining the list of 'chromosomes'. In the case of SARS-CoV-2, we simply list the sequences as 'chromosome 1' . This file must also be compressed

Each of the manifest files will need to be edited to add your own accessions in order to link these sequences to your existing objects. The following lines should be customised:
```
STUDY   PRJEB#####
SAMPLE  ERS#######
RUN_REF ERR#######
```

```{note}
Where possible, we recommend including a `RUN_REF` to link the sequence back to the raw read data it was built from.
```

As we did with reads, we will first validate our submission using the `-validate` flag.

```bash
java -jar webin-cli-4.2.0.jar -context genome -manifest hCoV-19_isolate_1_manifest.txt -userName user -password pass -test -validate
```

If this passes validation, we can replace the `-validate` flag with `-submit` to perform the submission.

```{warning}
Please use the `-test` flag to submit to our test service
```

```bash
java -jar webin-cli-4.2.0.jar -context genome -manifest hCoV-19_isolate_1_manifest.txt -userName user -password pass -test -submit
```

## Webin-CLI-REST

A new JSON-based REST service was introduced this year specifically for the submission of SARS-CoV-2 sequences. In this service, sequences are not held in fasta files - rather, they are included directly in the JSON payload itself, greatly simplifying the process of submission. This is only possible due to the small size and relatively low complexity of the genome. For more information on this system, including useful code snippets, please see our [documentation here](../help_and_guides/webin-cli-rest.html).

:::{tabbed} Unix/MacOS
```bash
cd $WORKSHOP/sequences/webin-cli-rest/
ls
```
:::

:::{tabbed} Windows
```
cd $WORKSHOP\sequences\webin-cli-rest\
dir
```
:::
