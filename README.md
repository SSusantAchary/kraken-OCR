# Kraken-OCR
kraken's main features are:

        Fully trainable layout analysis and character recognition
        Right-to-Left, BiDi, and Top-to-Bottom script support
        ALTO, PageXML, abbyXML, and hOCR output
        Word bounding boxes and character cuts
        Multi-script recognition support
        Public repository of model files
        Lightweight model files
        Variable recognition network architectures

# Installation

When using a recent version of pip all dependencies will be installed from binary wheel packages, so installing build-essential or your distributions equivalent is often unnecessary. kraken only runs on Linux or Mac OS X. Windows is not supported.

# Install the latest 1.0 release through conda:

$ wget https://raw.githubusercontent.com/mittagessen/kraken/master/environment.yml
$ conda env create -f environment.yml

or:

$ wget https://raw.githubusercontent.com/mittagessen/kraken/master/environment_cuda.yml
$ conda env create -f environment_cuda.yml

# for CUDA acceleration with the appropriate hardware.

It is also possible to install the same version from pypi:

$ pip install kraken

Finally you'll have to scrounge up a model to do the actual recognition of characters. To download the default model for printed English text and place it in the kraken directory for the current user:

$ kraken get 10.5281/zenodo.2577813

# A list of libre models available in the central repository can be retrieved by running:

$ kraken list

# Quickstart

Recognizing text on an image using the default parameters including the prerequisite steps of binarization and page segmentation:

$ kraken -i image.tif image.txt binarize segment ocr

To binarize a single image using the nlbin algorithm:

$ kraken -i image.tif bw.png binarize

To segment a binarized image into reading-order sorted lines:

$ kraken -i bw.png lines.json segment

To OCR a binarized image using the default RNN and the previously generated page segmentation:

$ kraken -i bw.png image.txt ocr --lines lines.json

All subcommands and options are documented. Use the help option to get more information.
Documentation

Have a look at the docs


# kraken is developed at Université PSL. Under Apache 2.0 License
