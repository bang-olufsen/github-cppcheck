# cppcheck

[![License](https://img.shields.io/badge/license-MIT_License-blue.svg?style=flat)](LICENSE)

Shell script for running the [Cppcheck](http://cppcheck.sourceforge.net) static code analysis tool for C/C++ source files. The script can either be executed from your build script or as part of GitHub pull requests with status updates. This makes it possible to add cppcheck as a required CI step. Currently only [Shippable](http://www.shippable.com) CI is supported for e.g. linking to build logs.

Input can either be a directory (e.g. ".") or specific files. For pull requests the special "diff" command can be parsed as argument to check only the changed files.

When all files are checked (e.g. as part of nightly builds) the Cppcheck badge is updated for the particular repository and branch. The badge is afterwards uploaded to [Dropbox](http://www.dropbox.com). For displaying the badge on e.g. your README.md copy the Dropbox link to the image and replace www.dropbox.com with dl.dropboxusercontent.com.

False positives can be suppressed using the cppcheck.txt file which must be located in the directory from where the script is executed. You can run the shell script directly from GitHub using e.g.:

```bash
bash <(curl -s https://raw.githubusercontent.com/bang-olufsen/cppcheck/master/cppcheck.sh) .
```
