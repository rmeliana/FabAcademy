# 2. Project Management

## Assignment

* Build a personal site describing you and your final project.
* Work through a git tutorial.

##What's Git and GitHub? How can I use them with mkdocs?:anguished:

And finally what is Markdown? :eyes:

I had a difficult time understanding the purpose of each one (Git, GitHub, mkdocs and markdown) and how to use them together to create a site.
Fortunately, in my work team, we were talking about interesting courses on Alura platform that we could take to improve our skills, and Git/GitHub course was one of them. I didn't conclude it, but it gave me a good knowledge about how Git and GitHub run.

## Research

* [**Git**](https://blog.betrybe.com/tecnologia/git-e-github/) is an open-source version control system, in other words, free of charge. It is used for creating a change history in the source code of software' development projects. It was designed by Linus Torvalds, the creator of the Linux operating system.

* [**Github**](https://blog.betrybe.com/tecnologia/git-e-github/) is a remote repository created as an online Git repository hosting service.

* [**MkDocs**](https://www.mkdocs.org/) is a fast, simple and downright gorgeous static site generator that's geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file.

* [**Markdown**](https://blog.bit.ai/what-is-markdown/) was created back in 2004 by John Gruber (of Daring Fireball) as an easy way for non-coders to write in a format that could be easily converted into HTML. John Gruber defines Markdown as, “A text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML)“.

## Creating a personal site: **for Windows**

* Install [Python 3.8.9](https://www.python.org/downloads/);

* Install [Git](https://git-scm.com/downloads) on Windows and let the Git Bash terminal be started;

* In Git Bash terminal, type `py --version` to see if the process worked out;

    <left>
    ![GitBash1](imgs/GitBash1.jpg){: style="height:100px"}
    </left>

* For downloading libraries from Git repositories, it's necessary the package manager of python, PIP. Type `pip --version` to see if it has already been installed;

    ![PIP](imgs/PIP.jpg){: style="height:100px"}

* For starting the website follow [Getting Started](https://www.mkdocs.org/getting-started/) page of MkDocs. It'll create all the basics files of the site on the local computer and give instructions of how to make changes in each page;

* For hosting it on GitHub follow the [Allythy tutorial](https://allythy.github.io/como-criar-documentacao-com-mkdocs) from "Deploy para o GitHub" topic until the end. It'll also generated the URL of documentation, similar of mine https://rmeliana.github.io/FabAcademy/;

* Locally, on the computer, changes in the site can be seen by the command 'mkdocs serve' and URL http://127.0.0.1:8000/....
<center>
![mkserve](imgs/mkserve.jpg){: style="height:100px"}
</center>

    However, once the files are on GitHub and it's made an update, a deployment process is needed in order to get updates published to GitHub Pages. For automating that, create a GitHub action following [Parker Erickson tutorial](https://parkererickson.github.io/portfolio/blog/MkDocsCD/);

    ![action](imgs/action.jpg)
    <figcaption align = "center"><b>Automatic GitHub deployment action</b></figcaption>

    !!! Important "Install all dependencies following instructions below."
        * Create a file called `requirements.txt` on the root of the main folder on the local computer and copy the text below in it.

        <center>
        ![](imgs/requirements.jpg){: style="height:300px"}
        </center>

        * Requirements text
        ```
          mkdocs>=1.1
          Pygments>=2.4
          markdown>=3.2
          pymdown-extensions>=7.0
          mkdocs-material-extensions>=1.0
        ```

        * Replace `pip install mkdocs-material` to `pip install -r requirements.txt` into `main.yml`:
        ```
        - name: Install dependencies
        run: |
            python -m pip install --upgrade pip
            pip install -r requirements.txt
        ```    


* Changing the theme: my personal site uses a theme called [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) that can be installed by the command `pip install mkdocs-material` on the computer system;

    <left>
    ![material install](imgs/material install.jpg){: style="height:80px"}
    </left>

    !!! Important "In `mkdocs.yml`, change theme for `material`"
        ```
        theme:
          name: material
        ```

## Advices
!!! Important ""
    * Git Bash: 
