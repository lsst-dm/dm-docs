# LSST Data Management Documents

Meta repository for all LSST Data Management documents developed on Github.
The repository is primarily configured to use Git submodules to refer to individual git repositories for each document using the provided hierarchy.
It is not expected that document files will be committed directly to this repository.

To check out a full document tree clone the repository and then initialize the submodules:

```
git clone https://github.com/lsst-dm/dm-docs.git
cd dm-docs
git submodule init
git submodule update
```

The `init`/`update` has to happen to pick up new submodules as new documents are added (this can be noted by pulling and seeing that `.gitmodules` has changed but there is now harm in redoing the `git submodule` commands).
Updates to old documents just need `git pull`.

The primary resource for baselined LSST Data Management documents is [LSST DocuShare](https://docushare.lsstcorp.org/docushare/dsweb/View/Collection-12).

For information on the LSST science pipelines see <https://pipelines.lsst.io>.
The LSST DM Developers Guide can be found at <https://developer.lsst.io>.

## Updating master branches

To update the master branches of all submodules do the following from the root directory of the repository:

```
git submodule foreach git checkout master
git submodule foreach git pull
```

Then commit these changes with:

```
git add */*
git commit
git push
```

In the future this updating will be automated to ensure that the repository always reflects the current state of the documentation.
