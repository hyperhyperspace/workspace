# Monorepo used for Hyper Hyper Space development.

This repo contains a [Yarn Workspace](https://classic.yarnpkg.com/en/docs/workspaces/) with all the Hyper Hyper Space packages configured as [Git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

The workspace uses the local versions of all the packages, that are located in the `@hyper-hyper-space` folder.

To clone and populate the monorepo:

```
git clone https://github.com/hyperhyperspace/workspace.git
```

and then inside the workspace repo:

```
git submodule init
git submodule update
```

This will populate the following repos:

- `workspace/@hyper-hyper-space/core`: the core library
- `workspace/@hyper-hyper-space/node-env`: additions to run the core library on NodeJS
- `workspace/@hyper-hyper-space/p2p-chat`: a chat engine based on HHS (WIP)
- `workspace/@hyper-hyper-space/p2p-chat-cli`: a console-based chat UI
- `workspace/@hyper-hyper-space/p2p-chat-web`: a web-based chat UI

You have to build the ones you want to use (even as depedencies) by doing

```
yarn build
```

This is very new so there may be glitches, please open an issue and we'll look into it!