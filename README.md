# skills-distance

A research project on occupational mobility for STARs — workers Skilled Through Alternative Routes (i.e. without a bachelor's degree). The question is about how we measure whether two jobs are "similar enough" that a worker could realistically move between them.

## Overview

Opportunity@Work's public "Reach for the STARs" methodology measures the distance between occupations using their O\*NET skill profiles. The method treats all 35 skills as equally important using a standard Euclidean distance metric. The idea behind this project is that skills aren't equally important to a given job. A gap in a skill the destination barely uses shouldn't count the same as a gap in a core one.

This project's 1st question is: if we weight each skill by how important it is to the destination occupation, relative to other skills, do you get a similarity measure that better predicts realized job transitions?

## Roadmap

- Build a directed grid of occupation→occupation pairs with wage and degree-screen context (ACS), staged in DuckDB. [done]
- Attach real observed transitions from CPS (ground truth) [done]
- Compute skill distances three ways: unweighted Euclidean (baseline), symmetric importance-weighted, and destination-importance-weighted. [in progress]
- Construct validation framework [upcoming]
- Compare how well each predicts observed moves [upcoming]
- Evaluate effect on STARs pathways/mobility [upcoming]

## Future Work

- Euclidean assumes skills are independent but O\*NET skills are correlated. It's double-counting clusters. Potentially use PCA to address?
- Euclidean measures magnitude. What if we just want skill profile shape? Could test cosine similarity/Manhattan distance

## Data Sources

- O\*NET skill-importance 30.1
- CPS ASEC 2014-2025
- ACS 1yr 2024
