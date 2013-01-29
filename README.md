gtr-gitter
==========

gtr-gitter -- a convenience script for git with cleanly separated work and repository directories (project and project.git)


What's in a name
----------------

You may have already guessed this: 'gtr' is pronounced 'gitter'.  The name chosen for a frequently used command line tool is very important.  In particular, a name which is awkward to pronounce slows you down and makes the entire tool feel cumbersome.  This may be psychosomatic but it is very real.

And so I present gtr, which is easy to type, and easy to say.  It makes a number of things in git easy too.

gtr serves two primary functions:

  1. Making it easy to work with repositories that have been separated from the working tree.  For example, if your project is called fuzzy-noodle, you can place your project repository in fuzzy-noodle.git, rather than in the hidden directory fuzzy-noodle/.git.  The working tree would still reside in fuzzy-noodle/.  Alternatively, project work-trees and repositories may be split into BASE/repos/fuzzy-noodle.git and BASE/projects/fuzzy-noodle directories.  gtr supports these arrangements and several others, including the default git arrangement.  It does so by detecting the location of the working tree and the respository according to a set of possible cases, and then passing the appropriate --git-dir and --work-tree options to git commands, so that you don't have too.  Nice.

  2. Providing a variety of convenience operations for common workflows.  These are listed in the usage section.  You might want to try `gtr log g` for lovely text-based commit graphs, or use `gtr squash` to quickly collapse several check-point commits.  Try `gtr pull upstream under` as a more explicit notation for integrating upstream changes.

In addition, gtr does not hide git.  In it's verbose mode, it displays every raw git operation it executes.  It serves to help you use git effectively, and the essence of the supported commands retain their git flavour.


Usage
-----

Place the gtr script somewhere on your search PATH for greater convenience.

    Usage:
        gtr setup user-name user-email
        gtr init [bare] project-name
        gtr clone [bare] project-url [alt-project-name]
        
        gtr new[-branch] branch-name
        gtr get branch-name
        
        gtr commit [message|!]
        gtr pull [source] (under|over)
        gtr merge [source] [squash]
        gtr squash wrt-check-point [message|!]
        
        gtr which (hash|branch|tag|remote|remote-branch)
        gtr log [g[1|2]]
        gtr check
        
        gtr add [paths]
        gtr stage
        gtr git ...
        gtr ...


