# mediawiki-repos

## Repository Configuration

### Example Repository Entry

```yaml
example_repo:
  versions: '1.35, 1.36'
  removed: false
  latest: true
  repo_url: 'https://github.com/example/example-repo'
  path: 'extensions/example'
  branch: 'REL1_X'
  commit: '1234abc'
  alpha_branch: 'main'
  shallow_submodules: true
  composer: true
```

### Parameters

1. versions:
   - A comma-separated list of versions for which the repository should be installed. If undefined, the repository will be installed for all versions.

2. removed:
   - Optional. If set to true, ensures the repository is absent.

3. latest:
   - Optional. If set to true, ensures the repository is the latest version. This means it would automatically be updated whenever puppet runs.

4. repo_url:
   - The URL of the Git repository.

5. path:
   - The path where the repository will be cloned.

6. branch:
   - The Git branch to be cloned. If '_branch_' is used, it adapts based on the main MediaWiki branch.

7. commit:
   - Optional. The Git commit to checkout. Requires branch to be set to a real branch that the commit exists on.

8. alpha_branch:
   - Optional. The alpha branch to be used if the MediaWiki core branch is 'master'. This is only needed if the repo's main branch is not also 'master'.

9. shallow_submodules:
   - Optional. If set to true, clones submodules with only the latest commit.
  
10. composer:
    - Optional. If set to true, runs Composer install for the repository.

**NOTE**: top-level keys in [mediawiki-repos.yaml](mediawiki-repos.yaml) **MUST** be sorted alphabetically.
