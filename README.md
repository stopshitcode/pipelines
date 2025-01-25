# SSC Pipelines

This is `workspace` branch of a multi project repository based on [orphan](https://git-scm.com/docs/git-checkout#Documentation/git-checkout.txt---orphanltnew-branchgt) branches.

## How To Use

Choose CI/CD Platform to see related documentation:

- [Drone CI](https://github.com/stopshitcode/pipelines/tree/drone%23master)
- [Bitbucket Pipelines](https://github.com/stopshitcode/pipelines/tree/bitbucket%23master)
- [GitHub Actions](https://github.com/stopshitcode/pipelines/tree/github%23master)
- [GitLab Pipelines](https://github.com/stopshitcode/pipelines/tree/gitlab%23master)
- [Woodpecker CI](https://github.com/stopshitcode/pipelines/tree/woodpecker%23master)

## Development

### Setup Workspace

```shell
mkdir --parents ~/w-stopshitcode/pipelines
cd              ~/w-stopshitcode/pipelines

git init
git remote add origin ssh://git@github.com/stopshitcode/pipelines.git

git fetch --all --prune

git checkout workspace

git worktree add bitbucket               bitbucket#master
git worktree add drone                   drone#master
git worktree add github                  github#master
git worktree add gitlab                  gitlab#master
git worktree add woodpecker              woodpecker#master

code SSC-Pipelines.code-workspace
```

### Notes

#### Add a new (platform) orphan branch

```shell
NEW_PLATFORM=...
#NEW_PLATFORM=bitbucket
git worktree add --orphan -b "${NEW_PLATFORM}#master" "${NEW_PLATFORM}"
cd "${NEW_PLATFORM}"
git commit --allow-empty -m "Initial Commit"
git push origin "${NEW_PLATFORM}#master"
```
