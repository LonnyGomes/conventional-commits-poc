# Conventional Commits POC

## Configuration

```javascript
module.exports = {
    plugins: [
        '@semantic-release/commit-analyzer',
        {
            preset: 'angular',
            releaseRules: [
                { type: 'docs', scope: 'README', release: 'patch' },
                { type: 'refactor', release: 'patch' },
                { type: 'style', release: 'patch' }
            ],
            parserOpts: {
                noteKeywords: ['BREAKING CHANGE', 'BREAKING CHANGES']
            }
        },
        '@semantic-release/release-notes-generator',
        {
            preset: 'angular',
            writerOpts: {
                commitsSort: ['subject', 'scope']
            }
        },
        '@semantic-release/changelog',
        '@semantic-release/git'
    ],
    ci: false
};
```

## References

Testing conventional commits tooling

-   [semantic-release](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#configuration) - useful for a CI-driven workflow
-   [standard version](https://github.com/conventional-changelog/standard-version) - manages releases at a local level
