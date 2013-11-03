make-profiler
=============

GNU Make with profiling feature

Adds options two options useful for profiling: -g/--graph and -u/--update-time.

When passing -g/--graph to GNU Make to generate a Graphviz file instead of building.
When -u/--update-time is given, GNU Make will print start and stop times for each of the targets to allow profiling.

This work is based on:
 - the "Create graph output" patch from http://savannah.gnu.org/patch/?7447
 - OpenShift guest <zlqhem@daum.net>'s "Update time" patches and fixes

TODO:
 - print profiling information in a more parsable format into a specific file
 - make graph output customizable via a <makefile>.graphcfg file that allows disabling the printing of specific targets/target types in the graph
 - evaluate using '--profile' instead of '--updte-time'
