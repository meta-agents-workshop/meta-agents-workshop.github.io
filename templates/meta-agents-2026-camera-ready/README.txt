Meta-Agents Workshop 2026 - Camera-Ready Template
================================================

Camera-ready deadline: November 20, 2026, Anywhere on Earth (AoE).
Workshop: December 11, 2026, Sydney, Australia.

All camera-ready papers must use this NeurIPS 2026 template.
Full papers: at most 10 pages of main text, including figures and tables.
Short papers: at most 4 pages of main text, including figures and tables.
References and appendices do not count toward the page limits.
Keep the main text self-contained and include a responsible-use statement.
The NeurIPS main-conference paper checklist is not required.
The workshop is non-archival.

Files
-----
neurips_2026.tex: editable example and formatting instructions; main file.
neurips_2026.sty: NeurIPS 2026 style with the workshop notice adapted.
meta-agents-2026-camera-ready.pdf: compiled example (included in the ZIP).

Usage
-----
1. Keep the .tex and .sty files together.
2. Replace the example title, authors, abstract, and body with your paper.
3. Keep these preamble settings:
   \usepackage[dblblindworkshop,final]{neurips_2026}
   \workshoptitle{Managing Agents that Manage Agents:
     Workshop on Responsible Use of Meta-Agents}
4. Restore author names, affiliations, author-identifying citations, and any
   acknowledgments removed during review. Final mode removes line numbers.
5. Compile with a TeX installation containing the packages used in the source:
   pdflatex -interaction=nonstopmode -halt-on-error neurips_2026.tex
   pdflatex -interaction=nonstopmode -halt-on-error neurips_2026.tex
   The output is neurips_2026.pdf.
6. Submit one PDF, including references and any appendices, through OpenReview:
   https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/Meta-Agents

Overleaf: upload the source files into a new project and select
neurips_2026.tex as the main document, using pdfLaTeX.

Do not change font sizes, margins, spacing, or other layout parameters.

Source and adaptation
---------------------
Based on the NeurIPS 2026 LaTeX template supplied by the organizers.
The style file retains its original attribution; the only functional changes
are the two workshop notice strings. The sample text has been adapted to the
Meta-Agents Workshop camera-ready requirements, and the main-conference
checklist has been omitted.

Workshop website: https://meta-agents-workshop.github.io/
