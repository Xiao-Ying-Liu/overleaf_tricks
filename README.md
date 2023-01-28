# Overleaf tricks

## Change citation for papers with three authors to "et al." style (with jpe bib style)
- Step 1: before `\begin{document}`, add ```\immediate\write18{cp `kpsewhich jpe.bst` .}``` (the space before `.` cannot be missing) to tell the shell to copy the "jpe.bst" file to your Overleaf project.
- Step 2: To the right of the **Recompile** button, you can find **Logs and output files**, click on this button and go to the bottom right, from **Other logs and files**, find "jpe.bst", click to download.
- Step 3: rename the downloaded file to "myjpe" and upload to your Overleaf project.
- Step 4: open the "myjpe.bst" file on Overleaf and find `FUNCTION {format.lab.names}`, under this section, change `numnames #3 > and` to `numnames #2 > and`, that is, for number of names over 2 (3 or more), use "et al." style.
- Step 5: change the `\bibliographystyle{jpe}` to `\bibliographystyle{myjpe}`.
- Step 6: recompile.

Ref:
  - To find the bst file: https://tex.stackexchange.com/questions/553385/where-to-find-apacite-bst-file-to-change-bibliography-style
  - To locate the format section: ChatGPT
