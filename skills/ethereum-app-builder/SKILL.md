---
name: ethereum-app-builder
description: "Scaffold and build Ethereum dApps using create-eth (Scaffold-ETH 2). Use when the user wants to: build an Ethereum app, create a dApp, start a web3 project, use Scaffold-ETH or create-eth, build something onchain, deploy a smart contract, deploy a smar contract with a frontend, or scaffold a full-stack blockchain application."
---

# Ethereum App Builder

Scaffold full-stack Ethereum dApps using create-eth (Scaffold-ETH 2). Guide the user through project setup, then hand off to the scaffolded project's built-in `AGENTS.md` for development.

## Scaffold Wizard

Walk the user through these questions before running `create-eth`. Use sensible defaults — don't force choices if the user has no preference.

### Step 1: Project Name

Ask what they want to build and choose a project name.

- Default: derive a kebab-case name from their description (e.g., "voting app" -> `voting-app`)
- Confirm the name before proceeding

### Step 2: Framework

Ask which Solidity framework they prefer.

- **Hardhat** (default) — JavaScript-based, beginner-friendly
- **Foundry** — Rust-based, faster compilation, Solidity-native tests

If the user has no preference, use Hardhat.

### Step 3: Extensions (optional)

Ask the user: "Would you like me to fetch the available extensions to see if any fit your project?"

- **If the user says yes:** Fetch the extension list from the sources in `references/extensions.md`, then suggest which extension(s) would be the best fit based on what the user is building. Present a short summary of the relevant options and recommend one.
- **If the user says no or has no preference:** Skip extensions entirely — use no extension.
- **Default behavior:** No extension. Only add one if the user explicitly opts in after seeing the list.

When fetching extensions, read the source files to get current extension names and descriptions. For more detail on a specific extension, fetch its README using the URL pattern in `references/extensions.md`.

### Step 4: Run create-eth

Build and execute the command:

```
npx create-eth@latest -s <framework> -e <extension> <project-name>
```

Flag reference:

- `-s hardhat` or `-s foundry` — select Solidity framework
- `-e <extension>` — add an extension (omit flag entirely if no extension)
- Last argument is the project name

Examples:

```bash
# Hardhat, no extension
npx create-eth@latest -s hardhat my-dapp

# Foundry with an extension
npx create-eth@latest -s foundry -e erc-20 token-app
```

### Step 5: Quickstart

After scaffolding completes, guide the user through the quickstart. Three terminals are needed:

1. **Start local chain:**

   ```bash
   cd <project-name> && yarn chain
   ```

2. **Deploy contracts** (new terminal):

   ```bash
   cd <project-name> && yarn deploy
   ```

3. **Start frontend** (new terminal):
   ```bash
   cd <project-name> && yarn start
   ```

The app will be available at `http://localhost:3000`.

## Defaults

When the user gives minimal input (e.g., "build me an ethereum app"):

- Project name: ask the user or infer from context
- Framework: Hardhat
- Extension: none
- Run quickstart immediately after scaffold

## Extension Discovery

When the user wants an extension, consult `references/extensions.md` for URLs to fetch the current extension list.

## Post-Scaffold Development

After scaffolding, the generated project includes an `AGENTS.md` file with comprehensive development guidance covering:

- Smart contract development patterns
- Frontend hooks and components
- Deployment workflows
- Code style conventions

Point the user to this file for all post-scaffold development questions.
