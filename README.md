# VSCode MongoDB Language Extension

The MongoDB language support for VSCode extensions.

![example](./example.png)

The MongoDB language is built for [the official MongoDB VSCode plugin](https://github.com/mongodb-js/vscode) that introduces a new `.mongodb` extension for its playground, but can be used as a MongoDB language support for any other plugin that needs the `.mongodb` extension.

## How to install

The MongoDB Language Extension is not released yet. To start using this extension with VSCode copy it into the `<user home>/.vscode/extensions` folder and restart VSCode.

## syntaxes/mongodb.tmLanguage.json

[The MongoDB Shell](https://docs.mongodb.com/manual/mongo/) language is a JavaScript-based query language that supports extended JSON, also called BSON.

The `mongodb.tmLanguage.json` file is derived from [TypeScript.tmLanguage](https://github.com/Microsoft/TypeScript-TmLanguage/blob/master/TypeScript.tmLanguage) and injected with MongoDB symbols from `mongodb-symbols.json`.

If you download a new version of the TypeScript grammar or update the MongoDB symbols you should update the MongoDB grammar by running the script:

`npm run update-grammar`

The script does the following changes:

- Parses the `TypeScript.tmLanguage` plist and builds `mongodb.tmLanguage.json`.
- Updates `.ts` file types, rule names and scope to `.mongodb`.
- Injects the `mongodb.tmLanguage.json` grammar with MongoDB symbols.

Compare `uuid` in `TypeScript.tmLanguage` and `mongodb.tmLanguage.json` to verify that a proper version of the grammar is being used.

## syntaxes/mongodb-symbols.json

The `mongodb-symbols.json` file contains symbols that are defined in [mongodb-ace-mode](https://github.com/mongodb-js/ace-mode/blob/master/index.js#L63-L263).

Note: ACE supports the [importing of .tmtheme and .tmlanguage files](https://github.com/ajaxorg/ace/wiki/Importing-.tmtheme-and-.tmlanguage-Files-into-Ace) for use in the editor. Probably `vscode-mongodb-language` can be a source of truth for other projects instead of requiring symbols from `mongodb-ace-mode`.
