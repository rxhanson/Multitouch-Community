# Multitouch Community
Issue and feature request tracking for the [Multitouch](https://multitouch.app) app

Go to the [Issues](https://github.com/rxhanson/Multitouch-Bugs/issues) tab to post bugs, feature requests, or questions.

If you're filing a bug, please include the following:
* MacOS version
* Multitouch version
* Detailed steps to reproduce

If you wish to contact me directly, feel free to send an email to multitouch@ryanhanson.dev

## Troubleshooting FAQ

#### The app stops recognizing gestures when my mac wakes from sleep and I have to restart the app.
If this happens, go to the settings tab and check the box for "Restart on wake" and this restart will happen automatically.
This isn't the default behavior because it typically just makes it longer for gestures to be available when waking from sleep, and not everyone has this issue.

#### The app stops recognizing gestures randomly after a while. When I restart the app, it works again. 
Not all mac setups are the same, so the solution to this can vary. Here's some things to try.
* Don't run other apps that listen to gesture information at the same time.
* Try disabling or enabling "Avoid private framework" in the settings tab. The private framework is necessary for Magic Mouse gestures, but trackpad gestures can function without it. Sometimes other apps or settings can interfere with how Multitouch receives touch input from the private framework.

## Localization

This repository holds the localization for both Multitouch and Rectangle Pro.

Translations live in the [`Localizations`](Localizations) folder as Xcode localization catalogs, one per language (`de.xcloc`, `fr.xcloc`, `ja.xcloc`, …). The file you edit is the XLIFF inside each catalog:

```
Localizations/<lang>.xcloc/Localized Contents/<lang>.xliff
```

You don't need the app source code or a Mac to contribute, but opening an `.xcloc` in Xcode gives you a convenient translation editor.

### Improving an existing translation

1. Fork this repo and open `Localizations/<lang>.xcloc` in Xcode (double-click it), or open the `.xliff` in any XLIFF 1.2 editor such as [Poedit](https://poedit.net) or a text editor.
2. Edit the `<target>` text for the strings you want to change. Use the `<note>` on each string for context.
3. Open a pull request.

### Adding a new language

Use the English catalog as a template. For example, for Italian (`it`):

1. Copy the catalog and rename the XLIFF:
   ```sh
   cd Localizations
   cp -R en.xcloc it.xcloc
   mv "it.xcloc/Localized Contents/en.xliff" "it.xcloc/Localized Contents/it.xliff"
   ```
2. Point it at the new language:
   - In `it.xcloc/contents.json`, set `"targetLocale" : "it"`.
   - In `it.xliff`, replace every `target-language="en"` with `target-language="it"`.
3. Translate each `<target>` and set its `state` to `"translated"`.
4. Open a pull request. Partial translations are welcome — untranslated strings fall back to English.

Use a standard language code for the folder name (e.g. `it`, `pt-BR`, `zh-Hant`). If you'd rather start from a catalog generated directly by Xcode, open an issue requesting the language and I'll add one.

### Guidelines

- Keep format specifiers exactly as they appear in the source: `%@`, `%d`, `%lld`, `%1$@`, etc. They can be reordered within the sentence, but not removed or changed.
- Keep `…` (ellipsis), keyboard symbols (`⌘ ⌥ ⌃ ⇧`), and app names (Multitouch, Rectangle Pro) as-is.
- Don't edit anything under `Source Contents` or the `<source>` elements. These are regenerated from the app on every export.
- Keep translations reasonably short, since many strings appear in menus and narrow settings panes.

When the apps add or change strings, the catalogs in this repo are re-exported, and new strings show up with `state="new"`.
