# Monorepo used for Hyper Hyper Space development.

This repo contains a [Yarn Workspace](https://classic.yarnpkg.com/en/docs/workspaces/) with all the Hyper Hyper Space packages configured as [Git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). You'll need [NodeJS](https://nodejs.org/) and [Yarn Classic](https://classic.yarnpkg.com/) to use the workspace.

The workspace uses local versions of all the Hyper Hyper Space-related packages, that are located in the `@hyper-hyper-space` folder.

The following versions of Node are supported: `^12.22.0 || ^14.17.0 || >=16.0.0`

To clone and populate the monorepo:
```
git clone https://github.com/hyperhyperspace/workspace.git
```

and then inside the workspace repo:
```
sh init.sh
```

This will populate all the repos, pull the latest `HEAD` and build all the projects that are libraries or re-usable data types, and thus necessary to build the applications in the workspace. At this point you can build and run the apps locally (`hyper-browser-web`, `pulsar-web`, `pulsar-cli`, etc.).

Web-based apps:
- `workspace/@hyper-hyper-space/hyper-browser-web`: A browser-based HHS environment
- `workspace/@hyper-hyper-space/pulsar-web`: Run a Pulsar node in the browser

Terminal-based apps:
- `workspace/@hyper-hyper-space/pulsar-cli`: Run a Pulsar node using NodeJS

Application-level datatypes:
- `workspace/@hyper-hyper-space/wiki-collab`: A collaboartively edited wiki
- `workspace/@hyper-hyper-space/chat-group`: A moderated chat group
- `workspace/@hyper-hyper-space/home`: A home folder, synchronized across a person devices, to hold spaces.
- `workspace/@hyper-hyper-space/pulsar`: An implementation of [José Orlicki](https://github.com/joigno)'s synthetic PoW algorithm, that uses a neglible amount of energy to achieve consensus, over HHS

Libraries:
- `workspace/@hyper-hyper-space/core`: the HHS core library
- `workspace/@hyper-hyper-space/node-env`: additions to run the core library on NodeJS
- `workspace/@hyper-hyper-space/sqlite`: SQLite storage backend  for HHS
- `workspace/@hyper-hyper-space/react`: React bindings for HHS objects

The old naive chat demo (deprecated):
- `workspace/@hyper-hyper-space/p2p-chat`: a chat engine based on HHS
- `workspace/@hyper-hyper-space/p2p-chat-cli`: a console-based chat UI
- `workspace/@hyper-hyper-space/p2p-chat-web`: a web-based chat UI

If you change the dependencies of any of the projects in the workspace (e.g. the `package.json` file), you need to run `yarn` in the workspace folder to update and link the dependencies in each project. You can rebuild all the libraries by running `build-deps.sh` (both steps have already been run by `init.sh`).