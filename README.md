#Configuring Vim to Chicken Scheme

##Introduction
Searching for tools to develop using the Chicken implementation of Scheme with
Vim I found some sparce material and I'll be centralizing what I find here.

##Chicken Swank
Swank is a protocol used for communication with some lisp system, this
protocol is useful for your IDE evaluate lisp code on a remote lisp running
an Swank server.

To configure Chicken Swank:

1. clone the [source code](https://github.com/nickg/swank-chicken) and execute
the 2 first steps in the README of the swank project. 

2. Now you must install and run the chicken-doc-admin package with:
  ```sh
  $ sudo chicken-install chicken-doc-admin
  $ chicken-doc-admin -i
  ```

3. Then inside the swank-chicken folder run:
  ```sh
  $ csi swank-chicken.scm
  ```
  and execute:
  ```lisp
  (swank-server-start)
  ```
  Now your Swank server should start.

##Slimv
While Emacs have SLIME, basically an awesome environment to develop general Lisp
implementations, Slimv try to brings some of the features available in SLIME to
vim. To run it for evaluate code directly inside vim you should install the
Chicken-swank server, described in the section before.

Trying to install Slimv cloning the git repository in my vimrc folder resulted
in an error during the plugin load. Searching for an explanation I get that the
code present in the Slimv github repository is not working properly with the
most recent versions of vim, but the
[code in development](https://bitbucket.org/kovisoft/slimv/overview) worked
well, so to use it:

1. Clone the depository using hg (mercurial) inside your `.vimrc` folder.

2. Open Vim and try to evaluate some block with `,d`, a CSI terminal should
open showing your block and the result of its execution.

For a more complete tutorial of how to use Slimv see
[here](http://kovisoft.bitbucket.org/tutorial.html)
