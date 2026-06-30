# skills-distance

A research project on occupational mobility for STARs — workers Skilled Through Alternative Routes (i.e. without a bachelor's degree). The question is about how we measure whether two jobs are "similar enough" that a worker could realistically move between them.

## The Idea

Opportunity@Work's public "Reach for the STARs" methodology measures the distance between occupations using their O\*NET skill profiles. The method treats all 35 skills as equally important: a plain Euclidean distance. The idea behind this project is that skills aren't equally important to a given job. A gap in a skill the destination barely uses shouldn't count the same as a gap in a core one.

So this project asks: if you weight each skill by how important it is to the destination occupation relative to other skills, do you get a similarity measure that better predicts the job moves people actually make?

## The Plan

- Build a directed grid of occupation→occupation pairs with wage and degree-screen context (ACS), staged in DuckDB.
- Attach real observed transitions from CPS (ground truth)
- Compute skill distances three ways: unweighted Euclidean (baseline), symmetric importance-weighted, and destination-importance-weighted.
- Compare how well each predicts observed moves

## Stack

Python (pandas, numpy), SQL, Plotly. Data from O\*NET, CPS ASEC, and ACS.

## Status

Data pipeline and exploratory analysis done; metric and validation in progress.
