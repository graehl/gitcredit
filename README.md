    usage: gitcredit [-h] [-f FILELIST] [-a AUTHORMAP] [-b BLAMEARG] [-o OUTDIR]
                     [-v VERBOSE]
                     [FILE [FILE ...]]

    given a list of input paths inside the git repo your current dir is in, give
    credit according to `git blame`, optionally creating a fresh git repo without
    meaningful history but with a commit per author

    positional arguments:
      FILE                  (args X for `git blame X`; added to --filelist file)

    optional arguments:
      -h, --help            show this help message and exit
      -f FILELIST, --filelist FILELIST
                            file containing lines X to `git blame X` (from the
                            current dir); - means STDIN - e.g. `find . >
                            /tmp/filelist`
      -a AUTHORMAP, --authormap AUTHORMAP
                            author mapping file - lines of e.g. gitauthorname =
                            Normalized Author <user@example.com> - order is commit
                            order for -o
      -b BLAMEARG, --blamearg BLAMEARG
                            -argument passed to git blame e.g. for copy detection
                            (which can be extremely slow) C CC or CCC
      -o OUTDIR, --outdir OUTDIR
                            outdir (if set) used to store author revision subdirs
                            outdir/0/ outdir/1/ ... with outdir/authors file
      -v VERBOSE, --verbose VERBOSE
                            > 0 means more logging
