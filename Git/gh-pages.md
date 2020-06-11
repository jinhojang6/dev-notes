## gh-pages
Publish files to a gh-pages branch on GitHub (or any other branch anywhere else).

```
yarn add --dev gh-pages
```

- https://www.npmjs.com/package/gh-pages

<br>

## Example

```
# /script/deploy.js

const { promisify } = require('util')
const { publish } = require('gh-pages')
const ghpublish = promisify(publish)

/* fix for "Unhandled promise rejections" */
process.on('unhandledRejection', err => { throw err })

const branch = 'gh-pages'
const org = 'jinhojang6'
const repo = 'status-tutorials'
/* use SSH auth by default */
const repoUrl = `git@github.com:${org}/${repo}.git`

/* alternative auth using GitHub user and API token */
if (process.env.GH_USER != undefined) {
  repoUrl = ( 
    'https://' + process.env.GH_USER +
    ':' + process.env.GH_TOKEN +
    '@' + `github.com/${org}/${repo}.git`
  )
}

const main = async (url, branch)=> {
  console.log(`Pushing to: ${url}`)
  console.log(`On branch: ${branch}`)
  await ghpublish('out', {
    repo: url,
    branch: branch,
    dotfiles: true,
    silent: false
  })
}

main(repoUrl, branch)
```

Update package.json
```
"deploy": "node scripts/deploy.js
```

<br>

## NextJS
Should update the base path
```
e.g.,
const basePath = '.'; 
const webpackBasePath = process.env.NODE_ENV = 'production' ? basePath : '';

const nextConfig = {
    assetPrefix: webpackBasePath,
```