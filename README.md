# cloud-me-pub-___

Registry index for the public cloud-me family (Cloud-Me-Pub) - same model as `CG-___`, `Fin-CM-___` and `cloudy-___`. This repo is an INDEX, not a container: it holds `repos.json` (the registry, a subset of _git-repos-master/repos.json), `clone.sh` (pick which repos to have locally) and one committed relative symlink per member (`<member> -> ../<member>`); the actual clones live as siblings in `~/git/`.

Parent hub: [cloud-me-___](https://github.com/diegonmarcos/cloud-me-___), the top hub of the cloud-me project (the owner's configs across the cloud).

## Members

- [cloud-me-pub-profiles](https://github.com/diegonmarcos/cloud-me-pub-profiles-___) - Hub of the cloud-me-pub-profiles family (Leaf.y, Nexus.z, Stark.x, Prf-Prs, _Lnktree): its own repos.json subset plus committed symlinks, same model as CG, Fin-CM and cloud. Was cloud-me-profiles (the b_Profiles, Lnktree and myAstro sources); content split into cloud-me-pub-profiles-prf-prs and cloud-me-pub-profiles-_lnktree 2026-10-28.
- [cloud-me-pub-shared](https://github.com/diegonmarcos/cloud-me-pub-shared) - Sources of the b_MyData group, split from front-projects (#1072); snapshot copy, paths mirror the original layout.

## Usage

```
./clone.sh                list what exists and what does not
./clone.sh <name>...      clone those, then link them
./clone.sh --all          clone every member
./clone.sh --link         relink whatever is already cloned
./clone.sh --relink       rewrite every link from the registry
./check-repos-sot.sh      verify repos.json against _git-repos-master
```

`repos.json` is a SUBSET of `~/git/_git-repos-master/repos.json` (the superset index of every repo this account owns): identical name/url/private/doc fields, checked by `./check-repos-sot.sh`.

## Hub submodule

This repo's parent hub is `cloud-me-___`, mounted as a git submodule at `0_hub/cloud-me-___` (one fixed path convention for every repo; URL https://github.com/diegonmarcos/cloud-me-___.git, pinned to the hub main). Only the upward link is a submodule; this hub keeps symlinks (not submodules) to its members, so there are no cycles. Source of truth: `repos.json` in _git-repos-master (`parent_hub` / `hub`, `_hub_submodule_doc`), guarded by `node repos-sot.js check-hubs`.
