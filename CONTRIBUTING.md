# Contributing

[AuthorCarpentry](http://authorcarpentry.github.io) is an open source project,
and we welcome contributions of all kinds:
new lessons,
fixes to existing material,
bug reports,
and reviews of proposed changes are all welcome.

## Contributor Agreement

By contributing,
you agree that we may redistribute your work under [our license](LICENSE.md).
In exchange,
we will address your issues and/or assess your change proposal as promptly as we can,
and help you become a member of our community.
Everyone involved in [Author Carpentry](http://authorcarpentry.github.io)
agrees to abide by our [code of conduct](CONDUCT.md).

## Editing Lesson Content

All lesson content is written in markdown (.md) files.  We use [mkpage](https://github.com/caltechlibrary/mkpage) 
to render lesson content into .html pages.  Install mkpage from the Caltech
Library repository at https://github.com/caltechlibrary/mkpage.  There is
a different mkpage available via rpm that won't work for our application.
While GitHub can render content, we use mkpage so lesson content can
be viewed independent from a web connection.  

## Working With GitHub

1.  Fork the `authorcarpentry/lesson-name` repository on GitHub.  

2.  Clone the repository to your local computer by using the "Clone"
    link at the top left corner of the repository page.  In a local
    terminal window type 'git clone *link*'

3.  Make your changes to the .md files using your favorite text editor.  

4.  Render your content by typing ./mk-website.bash

5.  (Optional) View your changes locally by typing 'ws' and pointing your web browser to http://localhost:8000

6.  Upload your changes to your GitHub account by typing ./publish.bash (Does a
    git commit and push)

7.  On the your GitHub repository site 'https://github.com/username/lesson-name' add a new branch by using the branch
    dropdown.  Choose something that describes the changes you've made like `fixing-typos-in-shell-lesson`
    or `adding-tutorial-on-visualization`.   

8.  Submit a pull request by clicking the 'New pull request' button, right next
    to the branch dropdown. 

If it is easier for you to send them to us some other way,
please mail us at [authorcarpentry@library.caltech.edu](mailto:authorcarpentry@library.caltech.edu).
Given a choice between you creating content or wrestling with Git,
we'd rather have you doing the former.

## Locations and Formats

Every lesson has a repository of its own, while individual topics are files
in that directory.  For example, the `shell-ecology` directory holding our
introduction to the shell for ecology contains the files `00-intro.md`, 
`01-filedir.md` and so on.  (We use two digits followed by a one-word topic 
key to ensure files
appear in the right order when listed.)

## Formatting of the material

To ensure a consistent formatting of the lessons, we recommend the following
guidelines:

- No trailing white space
- Wrap lines at 80 characters (unless it breaks URLs)


## FAQ

*Where can I get help?*

Mail us at [authorcarpentry@library.caltech.edu](mailto:authorcarpentry@library.caltech.edu)     
