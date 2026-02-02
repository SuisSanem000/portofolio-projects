# **Pnpm Workspace**

 To get started, let’s make sure you have PNPM installed. The [official docs have an installation page.](https://pnpm.io/installation "Installation | pnpm")

## **Setting up the Workspace structure:**

1. Create a new folder named pnpm-workspace (An optional name). cd into it and then run pnpm init to generate a top-level package.json

```bash
> mkdir pnpm-workspace
> cd pnpm-workspace
> pnpm init
```

2. Create an apps and packages folder within pnpm-workspace.

```bash
> mkdir apps packages
```

3. Create a `pnpm-workspace.yaml` into the root of the project.

```bash
> touch pnpm-workspace.yaml
```

4. Defining workspace structure in `pnpm-workspace.yaml` file.

```yaml
packages:
  - 'apps/*'
  - 'packages/*'
```

Usually, in a workspace/monorepo you want to run commands from the root of the repository to not have to constantly switch between folders. PNPM workspaces have a way to do that, by passing a filter argument, like:

```bash
> pnpm --filter <package-name> <command>
```

## **Consuming our packages from the apps**

This pnpm command adds ui-library packages to the dependency in the `apps/react-app/package.json`

```bash
> pnpm add ui-library --filter react-app --workspace
```

## **More information**

[Setup a Monorepo with PNPM workspaces and speed it up with Nx! | by Juri Strumpflohner | Nx Devtools](https://blog.nrwl.io/setup-a-monorepo-with-pnpm-workspaces-and-speed-it-up-with-nx-bc5d97258a7e#6ad2 "Setup a Monorepo with PNPM workspaces and speed it up with Nx! | by Juri Strumpflohner | Nx Devtools")

### **Clone and run this sample project**:

```bash
> git clone git@gitlab.com:testprojectsgroup/web/pnpm-workspace.git
> cd pnpm-workspace
> pnpm install
> pnpm run --filter react-app dev
```


Run client: 
pnpm run --filter client dev
