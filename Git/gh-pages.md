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

<br>

## References

- [https://medium.com/@anotherplanet/git-tips-next-js-github-pages-2dbc9a819cb8](https://medium.com/@anotherplanet/git-tips-next-js-github-pages-2dbc9a819cb8)
- [Building a Static Single Page Application with JavaScript, for GitHub pages and more](https://medium.com/swlh/building-a-static-single-page-application-with-javascript-for-github-pages-and-more-eb568b436bea#8f76)
- [Next.js 에서 Static 파일 배포](https://medium.com/@itstedpark/next-js-%EC%97%90%EC%84%9C-static-%ED%8C%8C%EC%9D%BC-%EB%B0%B0%ED%8F%AC-86c9ae0f952f)