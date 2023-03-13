# GitHub Action: Clone Private GitHub Submodule

This action clones a private GitHub submodule using SSH deploy keys. The action sets up the deploy key, clones the submodule using SSH, and then sets the submodule URL to use HTTPS instead of SSH.

## Prerequisites

Setup [deployment keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys).

## Usage

This action can be used in your GitHub workflow by adding the following to your workflow file:

```yaml
- name: Clone private submodule
  uses: pietrobolcato/clone-private-github-submodule@v1
  with:
    ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
    module_link: my-organization/my-repo
    module_path: path/to/module
```

Where:

#### `ssh_private_key`

**Required** The private SSH key to use for authentication.

#### `module_link`

**Required** The link to the module to clone, in the format: my-organization/my-repo

#### `module_path`

**Required** Path where the module is located, relative to the root of the repository
