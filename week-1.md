# **Haskell:** Installation, running, and basic usage

Before I get into the installation, it should be noted that I'm running Haskell on Ubuntu 20.04. Odds are most of what I say in this section will port to other *NIX operating systems, but Windows and other OSs without apt-get may do better to seek installation advice elsewhere.


### *Installation*

Fortunately for Ubuntu, installing Haskell is exceedingly easy. All you need to do is run the following:
`sudo apt-get install haskell-platform`
and you should be in the clear.
If it starts spitting errors at you, you may try running the following:
`sudo apt-get update`
and then retrying the first command. If this command gives you errors, you are likely running an archaic distrobution and, while you may still be able to install Haskell from [https://www.haskell.org/downloads/](https://www.haskell.org/downloads/)
Installing Haskell in this way allows for global access to the interactive Haskell environment and compiler, so if you're used to interfacing with Python via command line, this will likely be the more natural of the two options.

If you want to install Haskell in with a more project-centric tool stack, then you can run:
`curl -sSL https://get.haskellstack.org/ | sh`
to install the full Haskell Tool Stack. It may be necessary to install curl with:
`sudo apt install curl`
before running the curl command.
If you choose to install Haskell in this way, you must replace the:
`ghci`
command from here on out with:
`stack exec ghci`
since all Haskell compilers and binaries are operated through the stack command.

The other tool that you'll need to install is BNFC, which automatically goes through your haskell files and adds new ones in order to expand them into fully usable data types.
To install BNFC, clone the git BNFC repository into a location you desire by running:
`git clone https://github.com/BNFC/bnfc`
Then, change directories into the 'bnfc' folder that was just created, and run:
`make`
This step requires having make installed, which is easy enough to do. After making the makefile, you should find the bnfc binary file in /usr/bin/ and be able to execute the
`bnfc`
command globally.


### *Running*

If Haskell has been properly, you should find a few new binary files in your /usr/bin/ directory called **ghc** and **ghci**. Furthermore, you should now be able to run:
`ghci`
globally, as you would cd, ls, or passwd.

Entering the command above should spit out something that looks similar to this:
> GHCi, version 8.6.5: http://www.haskell.org/ghc/  :? for help
> Prelude> 
From here, you can now interact with Haskell as one would through the interactive Python shell. In order to make sure this is the case, you can enter '1+1', and it should return a 2.


[***Next week: Basic Haskell***](https://github.com/lblack1/cpsc354-blog/blob/main/week-2.md)
