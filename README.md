# github-gitlab-release-package-manager

Every github/gitlab release with file `RELEASE.json` can distribute a release for its packages.

imagine repo `github.com/aria3ppp/my-packages`:
- every release must have a `RELEASE.json` contain these properties:
```json
{
  "name": "my-amazing-package",
  "version": "v0.1.0",
  "release_id": "some uuid or whatever: a package id must be the same for the previous version and next version of the same pacakge in order to that package get updated",
  "dependencies" : {
    "gitlab.com/username/dependency-package": "v1.0.0",
  }
}
```
- users can download and install release packages with the repo and package name or package id
```shell
release repo add my-packages github.com/aria3ppp/my-packages
release install my-packages/my-amazing-package
release update my-packages/my-amazing-package
release update # to update all packages from all repos
```
