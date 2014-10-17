#!/bin/sh

MULTIMARKDOWN=${MULTIMARKDOWN:-kramdown}

rm -f index.html
cp head.in index.html
$MULTIMARKDOWN body.md >> index.html
cat tail.in >> index.html
