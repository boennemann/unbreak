# :broken_heart: unbreak :heart:

> Don’t leave me in all this pain. Don’t leave me out in the rain.

_Note: At this point `unbreak` is an idea without implementation._

`unbreak` aims to automatically update code so it stays compatible with its dependencies across [~~major~~](https://twitter.com/boennemann/status/597862058517000194) breaking version changes. In fact `unbreak` doesn’t do that all by itself. Rather it provides a standardized way for authors to attach transforms to a certain module and for consumers to execute them.

There are great tools like facebook’s [jscodeshift](https://github.com/facebook/jscodeshift) or substack’s [falafel](https://github.com/substack/node-falafel) that we can use to write such transforms.

For a module called `my-module` the author may publish a new module with the "unbreak" prefix – `unbreak-my-module` – that contains a transform for every major version that the package has.

_To encourage the use of semver `unbreak` supports transforms for major versions only._

_Transforms are published as a separate module so it's not necessary to add transformation tools as dependencies to the original module._

If you then run `unbreak` against your project it will look at the `npm outdated` output, update dependencies, find available transforms and correctly apply them to your codebase.
