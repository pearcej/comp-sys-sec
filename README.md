Computer Systems Security: Planning for Success
===============================================

This book is an interactive version of Ryan Tolboom's [Computer Systems Security: Planning for Success](https://web.njit.edu/~rt494/security/). We are very grateful to Ryan Tolboom for his work in writing this work and for releasing it under the
[Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)](http://creativecommons.org/licenses/by-nc-sa/4.0)
since his work forms the core of this interactive book.

We are extremely grateful to Berea College's internship program and the superb Berea College students who converted this book to PreTeXt in Summer 2025.

How to use this book
====================

- The generic version of this book is located at [https://runestone.academy/ns/books/published/comp-sys-sec/index.html?mode=browsing](https://runestone.academy/ns/books/published/comp-sys-sec/index.html?mode=browsing).
- Instructors who wish to use this book go to [https://runestone.academy/](https://runestone.academy/) and make an account using "comp-sys-sec" as the base book.
- Those wishing to report bugs or suggest improvements can do so at [https://github.com/pearcej/complex/issues](https://github.com/pearcej/comp-sys-sec/issues).

Licensing
=========

.. raw:: html

  <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">
  <img alt="Creative Commons License" style="border-width:0"
  src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />
  <span xmlns:dct="http://purl.org/dc/terms/" property="dct:title"><em>
  On Complexity</em></span> by Jan Pearce is licensed under a <a rel="license"
  href="http://creativecommons.org/licenses/by-nc-sa/4.0/">
  Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.


More about this book
====================

This book is build with PreTeXt, we used the [PreTeXt](https://pretextbook.org/) authoring system.  The source code for this book is available at [https://github.com/pearcej/comp-sys-sec](https://github.com/pearcej/comp-sys-sec). Contributions are welcome!  If you find a bug, or have a suggestion for improvement, please open an issue on the GitHub repository.
If you would like to contribute, please fork the repository and submit a pull request.  If you are not familiar with GitHub, please see the [GitHub documentation](https://docs.github.com/en/get-started/quickstart) for help.

To compile the book as an accessible website, run `pretext build web` in a terminal from any directory of this project.

To preview your output, run `pretext view web`.

To deploy your output to GitHub pages, run `pretext deploy`.

To compile a pdf, run `pretext build print`.

---

Below you will find some advice for working with PreTeXt, including help with using the [PreTeXt Codespace](https://github.com/PreTeXtBook/pretext-codespace) online editor through GitHub if you don't want to install the required software on your own computer.


## Learning PreTeXt

See the [PreTeXt documentation](https://pretextbook.org/documentation.html) for links to a variety of resources.

We also recommend browsing through the [annotated sample article](https://pretextbook.org/examples/sample-article/annotated) and [annotated sample book](https://pretextbook.org/examples/sample-book/annotated/) if you want to find examples and see the PreTeXt source for those examples quickly.

## Using GitHub Codespaces

GitHub Codespaces are a way to set up your whole authoring system entirely in your browser.  In case you are not already reading this inside a codespace, you can create one specifically designed for authoring in PreTeXt by using [this template](https://github.com/PreTeXtBook/pretext-codespace).

### Important: how to save your files

The most important thing to remember when authoring in a codespace is that you are making all your edits on a *virtual machine* off in some remote server farm.  This means there is an extra step to save your files.  You can save files in the editor (in your browser), but this just saves them to that virtual machine.  To make sure you can access these files, even if the virtual machine goes away, you need to sync them to github.com.  This is done by *committing* your changes and then *pushing* those commits (or "syncing" them).  You might see a warning when you restart your codespace that you have "uncommitted changes" -- make sure you commit them when you are done working.

### Troubleshooting: Latex-images and pdfs

We have tried to keep the codespace small (so it starts up quickly and doesn't eat through your monthly storage allotment), so we do not include a full TeXLive distribution.  We have tried to include most packages and fonts you are likely to need to generate images using `<latex-image>` elements, and to generate PDF print output.  However, if you run into a situation where the LaTeX gives errors about packages missing (like it cannot find a `mypackage.sty` file), here is what you should do.

1. To quickly resolve the issue yourself, open a terminal (``Ctrl+Shift+` ``) and use the TeXLive Package Manager to install the missing package.  
    a. If you know that the package is called `mypackage` then enter the following two lines:

    ```bash
    tlmgr install mypackage
    tlmgr path add
    ```
    b. If you don't know the name of the package, but know it should contain `mypackage.sty`, then you can search using

    ```bash
    tlmgr search --global --all "mypackage.sty"
    ```

2. To ensure that you don't have to repeat this step every time you recreate the codespace, add the package name to the list of installs inside the file `.devcontainer/installLatex.sh` which gets run every time a codespace is created.

3. Better yet, post the name of the missing package to this [GitHub issue](https://github.com/PreTeXtBook/pretext-codespace/issues/21) and we will add it to the devcontainer.  This has the advantage that you will still get updates that other authors submit (if you edit the `installLatex.sh` file, then it won't be updated when you run `pretext update`).

### Troubleshooting: sageplot images

By far the largest space-hog in a PreTeXt authoring environment is SageMath, which is only required if you generate images using sageplots.  By default, SageMath is not installed in a PreTeXt codespace, but it should be easy to install if you need it.  

Just open the command palette (`Ctrl+Shift+P` of `F1`) and search for "PreTeXt: Install SageMath".  This will also update the `.devcontainer/devcontainer.json` file so that the next time you create a codespace for this project, it should install automatically.