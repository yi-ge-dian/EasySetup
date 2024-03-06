# hexo

安装git

```bash
brew install git
```

安装nodejs，使用nvm

```bash
brew install nvm
nvm install --lts
```

安装hexo

```bash
npm install -g hexo
```

RSS

```bash
npm install hexo-generator-feed --save
/atom.xml
```

部署

```bash
npm install hexo-deployer-git --save

Deployment
Docs: 
https://hexo.io/docs/one-command-deployment
deploy:
type: 'git'
repo: xxxxx(need to replcae)
branch: master
```

