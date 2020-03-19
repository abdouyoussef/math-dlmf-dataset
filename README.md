# math-dlmf-dataset
This is a twin math dataset consisting of a per-expression data subset, and Simple-XML data subset (with marked-up sentences and marked-up math). 

This twin dataset is derived from the <a href="http://dlmf.nist.gov"> Digital Library of Mathematical Functions</a> (DLMF) of <a href="http://www.nist.gov">NIST</a>.

The per-expression data subset is structured and labeled at fine granularity. For each math equation or expression in the DLMF, there is a record that provides a number of related elements, both contextual and annotational. The Simple-XML data subset consists of "Simple XML" files, where the contents of each Simple XML file are organized as marked-up sentences within the marked-up hierarchy of paragraphs/subsections/sections inherited form the original DLMF XML files (derived from LaTeX source files using Bruce Miller's <a href="http://dlmf.nist.gov/LaTeXML/" title="" class="ltx_ref ltx_font_typewriter">LaTeXML</a> tool). Each sentence consists of its text and math XML-elements with their own unique IDs. 

The per-expression data subset is organized by records, one per equation and one per mathematical expression. Each equation-record starts with the keyword "Equation" and ends with the keyword "End-equation" on separate lines, and has separate fields, where each field is a name:value pair. The name of each field is a meaningful string, and the value is a text string that can be a LATEX encoding, an ID, or a sequence of name:value fields. The record of an expression is identical to that of an equation except that it starts with the keyword Expression, ends with the keyword End-expression, and does not have the following fields: equation-number, permalink, constraints, symbols-used, and symbols-defined.

In the Simple-XML data subset, each section of the DLMF is a lean XML file, structured as a tree of section and subsections. Each subsection consists of paragraphs, and each paragraph is a sequence of marked-up sentences that contain text and/or marked-up math elements. Each sentence element has valuable XML attributes, including the xml-id attribute of the sentence.

Both twin datasets have a directory structure that mirrors the directory structure of the DLMF, that is, each chapter is a directory of files, one file per section, where the chapters are numbered 1-36, and the section files also have numeric names. For example, file "2.3.txt" in is the (text) file corresponding to Section 3 of Chapter 2, and containing the records of the equations and math expression of Section 3 of Chapter 2 of the DLMF. Similar, 


The full context of each equation or expression is easily and quickly derivable from the twin datasets, which enables users to identify and fully extract the sentence containing a given equation/expression, as well as neighboring sentences
or full paragraphs, for contextualized processing needed in many mth language processing (MLP) tasks.
