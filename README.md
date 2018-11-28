Overtone Installations for Mac (5-10 min).
======

# Part I. Software Installation
1.	Install Homebrew
2.	Install Supercollider and get it ready:
⋅⋅1. Copy the following to the window “Untitled” on the left side:
~~~
s.boot;
s.options.maxLogins = 50
~~~
⋅⋅2.	Click Language > Evaluate File

3.	Install Atom
4.	In Terminal, type: brew cask install java
5.	In Terminal, type: brew install clojure
6.	In Terminal, type: brew install leiningen

Part II. New Project and Setting Configuration

In Terminal, type:
1.	`cd Desktop`
2.	`lein new myproj`
NOTE: *myproj* can be changed to whatever name you desire; remember to change it in subsequent places as well!

3.	`cd myproj`
4.	`atom project.clj`
NOTE: Atom (text editor) will open. Replace whatever is in the project.clj file with the code below, and save and quit:

~~~
(defproject myproj "1.0"
  :dependencies [[org.clojure/clojure "1.8.0"][overtone "0.10.3"]])
~~~

5.	`lein deps`
6.	`atom src/myproj/core.clj`
NOTE: Atom (text editor) will open. Replace whatever is in the core.clj file with the code below (which creates music), and save (don’t quit).
In the future, 	this is the file that you should change to create your own music!

~~~
(ns myproj.core
  (:use [overtone.core]))
(definst baz [freq 440] (sin-osc freq))
~~~

# Part III. Run Project

In Terminal, type: 
1.	`lein repl`
2.	After the prompt user =>, type `(use 'overtone.live)` and hit Enter.
3.	`(use ‘myproj.core :reload)` + Enter.
4.	`(baz)` + Enter.
NOTE: *baz* can be changed to whatever name you desire; remember to change it in other places as well (in the core.clj file)!
5.	You should hear a sound if your file loaded correctly. Type `(stop)` and hit Enter to stop the sound.

# After...
After the installation and creation of your first project…

* Part I only needs to be done the first time you install this!
* Part II should be done every new project you start. Then, move on to Part III.
* Otherwise, when you are merely making changes to your projects, just do
⋅⋅1. (Terminal) `cd Desktop`
⋅⋅2. (Terminal) `cd myproj`
⋅⋅3. `atom src/myproj/core.clj` (and modify the file)
If you want to try modifying the file to see how you can test another code, a good example is Dave’s class code. Just copy and paste in core.clj! Remember to save the file!
⋅⋅4. Perform Part III.


