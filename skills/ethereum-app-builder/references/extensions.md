# Extension Discovery Sources

Always fetch from these sources at runtime to get up-to-date information.

## Curated Extensions

Fetch the curated extension list (maintained by Scaffold-ETH team):

```
https://raw.githubusercontent.com/scaffold-eth/create-eth/main/src/extensions/create-eth-extensions.ts
```

## Third-Party Extensions

Fetch community/organization extensions:

```
https://raw.githubusercontent.com/scaffold-eth/create-eth/main/src/extensions/organizations.ts
```

## SpeedRun Challenges

Fetch SpeedRunEthereum challenge extensions:

```
https://raw.githubusercontent.com/scaffold-eth/create-eth/main/src/extensions/challenges.ts
```

## Individual Extension READMEs

To get details about a specific extension, fetch its README:

```
https://raw.githubusercontent.com/scaffold-eth/create-eth-extensions/<branch>/README.md
```

Replace `<branch>` with the extension branch name (typically matches the extension name from the curated list).
