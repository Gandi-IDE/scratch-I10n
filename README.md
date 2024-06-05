# scratch-l10n


## How to Contribute Translations？

1. All localization-related files are located in the editor directory.
2. Currently, Gandi IDE only supports English and Chinese localization. Please provide translations for other languages based on the English localization.
3. Submit your translations via a pull request.
4. If you are not familiar with GitHub, please send the translated content via email or contact the official team or mod team on the Gandi Discord server.

- Email: gandi.ide@gmail.com
- Discord: [https://discord.gg/gandi](https://discord.gg/gandi)


## Using scratch-l10n in development

#### Installation
```bash
npm install --save-dev scratch-l10n
```

#### Basic Use
```js
import locales, {localeData, isRtl} from 'scratch-l10n';
import editorMessages from 'scratch-l10n/locales/editor-messages';
```
* `locales`: currently supported locales for the Scratch project
* `isRtl`: function that returns true if the locale is one that is written right-to-left
* `localeData`: locale data for the supported locales, in the format accepted by `addLocaleData` required by `react-intl`
* `editorMessages`: the actual message strings for all supported locales for a particular resource. `editorMessages` collects all the strings for the interface, extensions and paint-editor.

#### Useful Scripts
scratch-l10n provides:
* `build-i18n-src`: script that uses babel and plugins to extract all `FormattedMessage` strings for translation. Combines the message from all the source files into one `en.json`
* `tx-push-src`: script to push the `en.json` file to Transifex. Requires that the environment variable `TX_TOKEN` is set with a value that has developer access to the Scratch projects on Transifex (i.e. Scratch Team only)

#### Versioning
scratch-l10n uses semantic versioning - breaking changes will increment the major version number, and new features (e.g. a new language) will increment the minor version number. However, the patch number is actually a datetime string. That way it's easy to see how recently the translations were updated.

In general, changes that require a PR (new functionality, new language) should increment the minor version. Pulling new translations from Transifex is automated and will commit to master directly.

#### Deprecations

We are moving away from using the `tx` cli, so the `.tx/config` file will eventually be deprecated.
