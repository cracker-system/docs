# Cracker Documents
Crackerの開発者向けドキュメントのリポジトリです。  

このドキュメントは[Docusaurus](https://docusaurus.io/)により作成され、GitHub Pagesにデプロイされています。  

ドキュメントを読む場合は以下にアクセスしてください。  

https://cracker-system.github.io/docs/

### デプロイ
GitHub Actionsにより、mainブランチにpushされると自動的にGitHub Pagesにデプロイされます。

### Installation

```
$ yarn
```

### Local Development

```
$ yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

```
$ yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

### Deployment

Using SSH:

```
$ USE_SSH=true yarn deploy
```

Not using SSH:

```
$ GIT_USER=<Your GitHub username> yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
