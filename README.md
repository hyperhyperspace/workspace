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
sh pull-all-heads.sh
```

This will populate the following repos:
- `workspace/@hyper-hyper-space/core`: the HHS core library
- `workspace/@hyper-hyper-space/node-env`: additions to run the core library on NodeJS
- `workspace/@hyper-hyper-space/sqlite`: SQLite storage backend  for HHS
- `workspace/@hyper-hyper-space/react`: React bindings for HHS objects

Application-level datatypes:
- `workspace/@hyper-hyper-space/chat-group`: A moderated chat group
- `workspace/@hyper-hyper-space/home`: A home folder, synchronized across a person devices, to hold spaces.
- `workspace/@hyper-hyper-space/pulsar`: An implementation of [José Orlicki](https://github.com/joigno)'s synthetic PoW algorithm, that uses a neglible amount of energy to achieve consensus, over HHS

Web-based UIs:
- `workspace/@hyper-hyper-space/hyper-browser-web`: A browser-based HHS environment
- `workspace/@hyper-hyper-space/pulsar-web`: Run a Pulsar node in the browser

Terminal-based UIs:
- `workspace/@hyper-hyper-space/pulsar-cli`: Run a Pulsar node using NodeJS


The old naive chat demo (deprecated):
- `workspace/@hyper-hyper-space/p2p-chat`: a chat engine based on HHS
- `workspace/@hyper-hyper-space/p2p-chat-cli`: a console-based chat UI
- `workspace/@hyper-hyper-space/p2p-chat-web`: a web-based chat UI

Next you need to get all the dependencies, the recommended way is to run
```
yarn
```
in the workspace root, so all the local references will be resolved correctly.

Next you have to build the ones you want to use (even as depedencies) by doing
```
yarn build
```
in each of the project folders (`core`, `code-env`, etc.)

You can build all the dependencies in one go by running the `build-deps` script manually.

This is very new so there may be glitches, please open an issue and we'll look into it!