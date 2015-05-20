GNU Make/Remake profiling feature
=================================

This document documents the GNU Make/Remake profiling concept, typical
use cases, example workflows when preforming profiling on makefiles and
various questions related to the profiling feature, its implementation
and its limitations/known issues.

Concept and use cases for profiling
-----------------------------------

Depending on the size of a Makefile, its complexity, its age, the
technical skill and the level of care that was taken to maintain the
build system in shape, or changing performance requirements for the
build system, maintainers of such systems can conclude they need a way
to better understand the system in question to be able to evaluate what
can be optimized in order to obtain better performance overall.

To better understand a GNU Makfile based build system and the places
where such a system might perform badly and could be improved,
information such as inter-target dependencies, target execution
ordering, time taken to complete specific steps is vital.

The profiling feature focuses on providing the time measurements
necessary in such an analysis.

For the feature to be useful and usable, common sense dictates what the
the characteristics of an ideal profiling feature are quite easy to spot
and can represent a good ideal model for the implemented feature:

 * profiling shall work on any platform the GNU make/remake works on
 * measuring should not should introduce any runtime delays in the
   any of the executed targets
 * data analysis should be very simple for both very simple or small
   makefiles, and, also, large scale complex makefiles
 * post data collection activities should be virtually inexistent and,
   if using an applcation such as Oocalc to visualize the data,
   simply importing the data should generate the corresponding graphs
 * data output should scale - large build system time measurements
   should work properly for both builds with a handful of targets, but
   also with huge target numbers
 * data outputs/measurement output should be both easy to parse at a
   casual glance by a human, but also easily machine parsable.

The typical profiling session for a relatively simple Makefile should be

 1. Run the make process the same command as in a regular build, but
    also add the flag to enable profiling
 2. Open Ooclac and import the resulted profiling output logs
 3. Generate the graph from the imported value

Example workflow
----------------

1. Generating the visualisation graph in Oocalc on a Linux system.

Comments, suggestions, questions
