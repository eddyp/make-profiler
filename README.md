make-profiler
=============

GNU Make with profiling feature

Adds options two options useful for profiling: -g/--graph and -P/--profile.

When passing -g/--graph to GNU Make to generate a Graphviz file instead of building.
When -P/--profile/--profile-format is given, GNU Make will print profiling information for each of the targets to allow profiling.

This work is based on:
 - Luke Shumaker's "Create graph output" patch from http://savannah.gnu.org/patch/?7447
 - OpenShift guest <zlqhem@daum.net>'s "Update time" patches and fixes

TODO:
 - make graph output customizable via a <makefile>.graphcfg file that allows disabling the printing of specific targets/target types in the graph
