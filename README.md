# math-dlmf-dataset
This is a twin math dataset consisting of a per-expression data subset, and Simple-XML data subset (with marked-up sentences and marked-up math). 

This twin dataset is derived from the <a href="http://dlmf.nist.gov"> Digital Library of Mathematical Functions</a> (DLMF) of <a href="http://www.nist.gov">NIST</a>.

The per-expression data subset, residing in <a href="https://github.com/abdouyoussef/math-dlmf-dataset/blob/master/One-Record-Per-Math-Expression.zip">One-Record-Per-Math-Expression.zip</a>, is structured and labeled at fine granularity. For each math equation or expression in the DLMF, there is a record that provides a number of related elements, both contextual and annotational. The Simple-XML data subset, residing in <a href="https://github.com/abdouyoussef/math-dlmf-dataset/blob/master/Simple-XML.zip">Simple-XML.zip</a>, consists of "Simple XML" files, where the contents of each Simple XML file are organized as marked-up sentences within the marked-up hierarchy of paragraphs/subsections/sections inherited form the original DLMF XML files (derived from LaTeX source files using Bruce Miller's <a href="http://dlmf.nist.gov/LaTeXML/" title="" class="ltx_ref ltx_font_typewriter">LaTeXML</a> tool). Each sentence consists of its text and math XML-elements with their own unique IDs. 

The per-expression data subset is organized by records, one per equation and one per mathematical expression. Each equation-record starts with the keyword "Equation" and ends with the keyword "End-equation" on separate lines, and has separate fields, where each field is a name:value pair. The name of each field is a meaningful string, and the value is a text string that can be a LATEX encoding, an ID, or a sequence of name:value fields. The fields' names and values are described in Tables 1 and 2 below. The record of an expression is identical to that of an equation except that it starts with the keyword Expression, ends with the keyword End-expression, and does not have the following fields: equation-number, permalink, constraints, symbols-used, and symbols-defined.

In the Simple-XML data subset, each section of the DLMF is a lean XML file, structured as a tree of section and subsections. Each subsection consists of paragraphs, and each paragraph is a sequence of marked-up sentences that contain text and/or marked-up math elements. Each sentence element has valuable XML attributes, including the xml-id attribute of the sentence.

Both twin datasets have a directory structure that mirrors the directory structure of the DLMF, that is, each chapter is a directory of files, one file per section, where the chapters are numbered 1-36, and the section files also have numeric names. For example, file "2.3.txt" in per-expression data subset is the (text) file corresponding to Section 3 of Chapter 2, and containing the records of the equations and math expressions of Section 3 of Chapter 2 of the DLMF. Similarly, file "2.3.xml" in the Simple-XML data subset is the lean sentence-oriented XML file corresponding to the contents of <a href="https://dlmf.nist.gov/2.3">Section 3 of Chapter 2</a> of the DLMF.

<table style="width:100%">
  <caption><b>Table 1</b>: Names, values and explanations of the fields of equation records.</caption>
<tr><th> Field Name </th> <th> Field Value and its Explanation </th> </tr>
<tr> <td> equation-number </td> <td> the unique equation number of the equation in DLMF    </td> </tr>
<tr> <td> permalink </td> <td> a unique URL of the equation </td> </tr>
<tr> <td> xml-id </td> <td> a unique XML ID of the equation within the DLMF  </td> </tr>
<tr> <td> tex </td> <td> LaTeX encoding of the equation, surrounded with double dollar signs </td> </tr>
<tr> <td> content-tex </td> <td> LaTeX encoding of the equation, but using DLMF-defined semantic Latex macros </td> </tr>
<tr> <td> constraints </td> <td> a number of name:value fields encoding the constraints of the equation, if any, in both \LaTeX and content-tex </td> </tr> 
<tr> <td> symbols-defined </td> <td> a number of name:value fields where the name is "symbol", and the value is in turn a number of name:value fields encoding and describing a math symbol in the equation, where the description gives the meaning of the symbol, which can be viewed as a symbol label in the ML sense </td> </tr>
<tr> <td> symbols-used </td> <td> similar to the symbols-defined values above, except that each symbol has an additional idref:value field where the latter value provides the ID where the original definition of that symbol is located in the DLMF</td> </tr>
<tr> <td> meaning </td> <td> the meaning or role of the symbol in question </td> </tr>
<tr> <td> idref </td> <td> a unqiue ID reference to the location where a symbol is initially defined in the DLMF </td> </tr>
<tr> <td> context </td> <td> a number of name:value fields that provide context-identifying references and titles of the textual units containing the equation, such as subsection and section titles, as detailed in Table 2</td> </tr>
</table>

<table style="width:100%">
  <caption><b>Table 2</b>: Names, values and explanations of the <u>context</u> fields of equation records.</caption>
<tr><th> Field Name </th> <th> Field Value and its Explanation</th> </tr>
<tr> <td> sentence-xmlid </td> <td>  a unique sentence ID within the \textit{Simple-XML} files of the DLMF </td> </tr>
<tr> <td> sentence-num-in-section </td> <td>  the in-section number of the sentence containing the equation </td> </tr>
<tr> <td> sentence-num-in-chapter </td> <td>  the in-chapter number of the sentence containing the equation </td> </tr>
<tr> <td> sentence-num-in-corpus </td> <td>  the in-corpus number of the sentence containing the equation </td> </tr>
<tr> <td> para-xmlid </td> <td>  a unique ID of the <i>physical</i> paragraph of the equation </td> </tr>
<tr> <td> para-num-of-sentences </td> <td>  the number of sentences in the physical paragraph of the equation </td> </tr>
<tr> <td> paragraph-xmlid </td> <td>  a unique XML ID of the <i>logical</i> paragraph of the equation </td> </tr>
<tr> <td> paragraph-title </td> <td>  the title of the logical paragraph of the equation </td> </tr>
<tr> <td> subsection-xmlid </td> <td>  a unique XML ID of the subsection containing the equation </td> </tr>
<tr> <td> subsection-title </td> <td>  the title of the subsection containing the equation </td> </tr>
<tr> <td> section-xmlid </td> <td>  a unique XML ID of the section containing the equation </td> </tr>
<tr> <td> section-title </td> <td>  the title of the section containing the equation </td> </tr>
<tr> <td> chapter-xmlid </td> <td>  a unique XML ID of the chapter containing the equation </td> </tr>
<tr> <td> chapter-title </td> <td>  the title of the chapter containing the equation </td> </tr>
</table>




The full context of each equation or expression is easily and quickly derivable from the twin datasets, which enables users to identify and fully extract the sentence containing a given equation/expression, as well as neighboring sentences
or full paragraphs, for contextualized processing needed in many mth language processing (MLP) tasks.
