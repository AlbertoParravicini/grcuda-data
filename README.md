# GrCUDA-Data

Archive repository for public data in GrCUDA: plots, datasets, benchmark results.

## Setup

Download it as `git submodule` of the main GrCUDA repository, in its root folder, using SSH:
```
cd $GRCUDA_ROOT;
git submodule add git@github.com:AlbertoParravicini/grcuda-data.git  # Using SSH
```
or using HTTPS:
```
cd $GRCUDA_ROOT;
git submodule add https://github.com/AlbertoParravicini/grcuda-data.git  # Using HTTPS
```

If you write scripts in GrCUDA (e.g. plotting scripts in `projects/resources/python/plotting`), assume that `grcuda-repo` is located in `grcuda`.

## Organization

There are 3 main folders: `plots`, `datasets`, `results`

1. `plots`: here we store all the plots produced from GrCUDA results and used in papers/presentations/etc. 
    * Please create a subfolder with the date in which plots are generated. Inside that folder, store plots as you prefer (e.g. creating other subfolders or using names to distinguish plots)
2. `datasets`: here we store large datasets used in benchmarks (e.g. graphs or matrices)
3. `results`: here we store results produced by GrCUDA, such as execution time traces. 
    * Please create a subfolder for each result type to identify the project it belongs to (such as `scheduling`, `scheduling-multigpu`, etc.)
    * If possible, avoid committing directly raw result files (e.g. `.csv`) and use a `.zip` instead.
    * Use this repository as a backup, and try to keep it well-organized. Push results that are meaningful, e.g. that have been used to create plots for a paper.
    * As convention, you can use a `*-full` directory and `*-full.zip` to store all results, even those that are not pushed to the remote repository (for example, `scheduling-full` and `scheduling-full.zip`). Then, move the results you want to backup remotely to the standard directory and zip (`scheduling` and `scheduling.zip`).

## Rules for branches/pushing/merging
1. Use branches if you are working on some new project, then merge to `master` once your data is stable (e.g. you have submitted a paper)
2. Data pushed to the remote repository should be seen as somewhat immutable. Avoid overwriting existing files unless you know what you are doing!
3. For file names, organization etc. see **Organization**