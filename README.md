# SVG-path-optimizer
Optimize path between cuts/etch in SVG files for laser engraver

## !!! - THIS IS A WORK IN PROGRESS - !!!

It is still not functional, estimated timeline is by the end of November 2024 to have a bare functional software in place

# Aim
The main goal of this software is to optimize the path for a laser engraver or a CNC machine, starting from a SVG vector file.
The software tries to minimize the "non-active" part of the path (i.e. the length of the travel path between cuts).

In the first version of the software the minimization algorithm will be rather simple and with shallow search, thus it might not find the absolute minimum path length, but it still improves significantly the work time in case of complex files with several separate paths.

# Algorithm
The core algorithm isolates individual paths in the SVG vector file and identifies its start and end point.
Taken a given path it seatches a second path which has its starting point closest to the end point of the first path.
It then rearranges the SVG vector file so that these paths are executed in succession

# Input
SVG file
It can have paths split between different layers and groups

# Output
SVG file
Unaltered properties
Paths rearranged within group and layers
Groups and layers maintained
