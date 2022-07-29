# GitOps Demo

![License](https://img.shields.io/badge/license-MIT-green.svg)

## Setup

- Create $HOME/bin directory
- Make sure $HOME/bin is in your path
- Copy the files and directory from cli to $HOME/bin

A few caveats

- We have only tested on GitHub
  - Email us if you run into any GitLab issues
- We have only tested on GitHub Codespaces (Ubuntu)
  - The cli should run on Mac – let us know if you hit issues
  - The cli will not run on Windows
- We use zsh and oh-my-zsh
  - If you’re using that, this will create tab completion
    - flt completion zsh > $HOME/.oh-my-zsh/completions/_flt
    - You’ll need to restart your shell
- For bash, add this to your .bashrc
  - source <(flt completion bash)
- You need to set the following env vars (add to .zshrc / .bashrc)
  - export PIB_REPO=yourGitLabsRepo
  - export PIB_BASE=pathToLocalGitRepo
- If you want to create a new cluster for gitops
  - Run flt create --gitops-only -c central-tx-atx-101
    - If you forget --gitops-only, the cli will try to create an Azure K8s cluster
    - We have an issue on our board to make that a separate command for simplicity
- To delete a cluster
  - rm -rf clusters/clustername cluster/clusterName.yaml

## flt Targets

- To change the targets
  - Start in an app directory (i.e. apps/imdb)
  - flt targets clear
    – remove all targets
  - flt targets add all
    - all must be the only target or ci-cd will fail
  - flt targets add region:east
    - or any KV pair from clusters/clusterName.yaml
  - flt targets remove region:east
- To deploy the new targets
  - flt targets deploy
- You should be able to run the docker run command in the GitHub action from the base of the repo
  - Email us if you run into any issues
- We can setup working sessions to add one of your apps and also drill into more details

Please don’t hesitate to reach out to us if you have any questions or hit any issues.

## Support

This project uses GitHub Issues to track bugs and feature requests. Please search the existing issues before filing new issues to avoid duplicates.  For new issues, file your bug or feature request as a new issue.

## Contributing

This project welcomes contributions and suggestions and has adopted the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct.html).

For more information see [Contributing.md](./.github/CONTRIBUTING.md)

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Any use of third-party trademarks or logos are subject to those third-party's policies.
