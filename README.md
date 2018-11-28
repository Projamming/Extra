Overtone Installations for Mac (5-10 min).
======

## Part I. Software Installation
1.	Install [Homebrew](https://brew.sh/)
2.	Install [Supercollider](https://supercollider.github.io/download) and get it ready:
- 1. Copy the following to the window “Untitled” on the left side:
~~~
s.boot;
s.options.maxLogins = 50
~~~
- 2.	Click **Language > Evaluate File**

3.	Install [Atom](https://atom.io/)

In **Terminal**, type:

4.	`brew cask install java`
5.	`brew install clojure`
6.	`brew install leiningen`

## Part II. New Project and Setting Configuration

In **Terminal**, type:
1.	`cd Desktop`
2.	`lein new myproj`

NOTE: *myproj* can be changed to whatever name you desire; remember to change it in subsequent places as well!

3.	`cd myproj`
4.	`atom project.clj`

NOTE: Atom (text editor) will open. Replace whatever is in the **project.clj** file with the code below, and save and quit:

~~~
(defproject myproj "1.0"
  :dependencies [[org.clojure/clojure "1.8.0"][overtone "0.10.3"]])
~~~

5.	`lein deps`
6.	`atom src/myproj/core.clj`

NOTE: Atom (text editor) will open. Replace whatever is in the **core.clj** file with the code below (which creates music), and save (don’t quit). In the future, 	this is the file that you should change to create your own music!

~~~
(ns myproj.core
  (:use [overtone.core]))
(definst baz [freq 440] (sin-osc freq))
~~~

## Part III. Run Project

In **Terminal**, type: 
1.	`lein repl`

After the prompt user =>, type:

2. `(use 'overtone.live)` and hit Enter.
3. `(use ‘myproj.core :reload)` + Enter.
4. `(baz)` + Enter.

NOTE: *baz* is the function that we are calling -- therefore, the name can change depending on our **core.clj** file!

5.	You should hear a sound if your file loaded correctly. Type `(stop)` and hit Enter to stop the sound.

## Part IV. After...
After the installation and creation of your first project…for subsequent project, please note the following:

* Part I only needs to be done the first time you install this!
* Part II should be done every new project you start. Then, move on to Part III.

* Otherwise, when you are merely making changes to projects,
in **Terminal**, type:
- 1. `cd Desktop`
- 2. `cd myproj`
- 3. `atom src/myproj/core.clj`
NOTE: Modify this file! If you want to try an example, I suggest looking at Dave’s [class code](https://github.com/Projamming/ClassCode/blob/master/11_13_inclass). Copy and paste in **core.clj**, and save the file.
- 4. Perform Part III.
