# BiDi Sync Pull Request Action

## Overview

Automatically synchronize content between repositories by creating a pull request when changes are detected.

## Usage

```yaml
name: Sync BiDi Repository

on:
  push:
    branches:
      - v1.0

jobs:
  sync-bidi:
    runs-on: ubuntu-latest
    steps:    
      - name: BiDi Sync Pull Request
      uses: rossrdme/pr-repo-to-folder@0.0.1
      with:
        bidi-sync-repo: yourusername/source-repo        # Required
        primary-repo: yourusername/target-repo          # Required
        primary-repo-folder: /docs                      # Required
        access-token: ${{ secrets.SYNC_PAT }}           # Required
        
        # Optional parameters below
        bidi-repo-folder: ''                            # Optional: defaults to root
        pr-base: main                                   # Optional: defaults to 'main'
        pr-branch: docs-sync                            # Optional: defaults to 'docs-sync'
        git-user-name: 'GitHub Actions Bot'             # Optional: custom git user name
        git-user-email: 'noreply@github.com'            # Optional: custom git user email
```
