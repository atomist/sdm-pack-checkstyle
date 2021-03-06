# @atomist/sdm-pack-checkstyle

[![atomist sdm goals](http://badge.atomist.com/T29E48P34/atomist/sdm-pack-checkstyle/0f2322af-4133-40d3-9882-3f99cb637390)](https://app.atomist.com/workspace/T29E48P34)
[![npm version](https://img.shields.io/npm/v/@atomist/sdm-pack-checkstyle.svg)](https://www.npmjs.com/package/@atomist/sdm-pack-checkstyle)


This Extension Pack for an Atomist SDM integrates [Checkstyle][], a static analysis tool for Java.

[API doc][api-doc]

[api-doc]: https://atomist.github.io/sdm-pack-checkstyle/ (API Doc for this pack)

[Checkstyle]: http://checkstyle.sourceforge.net/ (Checkstyle tool)

## Usage

1. First install the dependency in your SDM project

```
$ npm install @atomist/sdm-pack-checkstyle
```

2. Install the support

```typescript
import { checkstyleSupport } from "@atomist/sdm-pack-checkstyle";

sdm.addExtensionPack(checkstyleSupport({
    enabled: true,
    checkstylePath: "<path to a downloaded checkstyle-VERSION-all.jar>",    
}));
```

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com][slack].

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist/sdm-pack-checkstyle/issues

## Development

You will need to install [node][] to build and test this project.

To run tests, define a GITHUB_TOKEN to any valid token that has repo access. The tests
will create and delete repositories.

Define GITHUB_VISIBILITY=public if you want these to be public; default is private.
You'll get a 422 response from repo creation if you don't pay for private repos.

### Build and Test

Command | Reason
------- | ------
`npm install` | install all the required packages
`npm run build` | lint, compile, and test
`npm run lint` | run tslint against the TypeScript
`npm run compile` | compile all TypeScript into JavaScript
`npm test` | run tests and ensure everything is working
`npm run clean` | remove stray compiled JavaScript files and build directory

### Release

To create a new release of the project, update the version in
package.json and then push a tag for the version.  The version must be
of the form `M.N.P` where `M`, `N`, and `P` are integers that form the
next appropriate [semantic version][semver] for release.  The version
in the package.json must be the same as the tag.  For example:

[semver]: http://semver.org

```
$ npm version 1.2.3
$ git tag -a -m 'The ABC release' 1.2.3
$ git push origin 1.2.3
```

The Travis CI build (see badge at the top of this page) will publish
the NPM module and automatically create a GitHub release using the tag
name for the release and the comment provided on the annotated tag as
the contents of the release notes.

---

Created by [Atomist][atomist].
Need Help?  [Join our Slack team][slack].

[atomist]: https://atomist.com/ (Atomist - Development Automation)
[slack]: https://join.atomist.com/ (Atomist Community Slack)
