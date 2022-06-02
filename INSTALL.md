# Install and Use
As explained in https://github.com/fluttercommunity/import_sorter/issues/60, the default setup is a bit slow. In order to run it fast, cd into your `hoodoo-software` directory and run the following   
```sh
git clone https://github.com/hoodoo-software/import_sorter.git
cd import_sorter
dart compile exe bin/main.dart -o bin/import_sorter
```
then add the executable path to your shell profile (`~/.zshrc`)
```profile
export PATH="$PATH:$HOME/__PATH_TO_THE_IMPORT_SORTER_REPO___/bin"
```
then make sure your new profile settings are applied, and go to a package
```sh
source ~/.zshrc
cd ../flutter-packages/packages/hoodoo_auth
```
you should now be able to run the following
```sh
import_sorter
```

If you use VSCode with the extension [`Run on Save`](https://marketplace.visualstudio.com/items?itemName=emeraldwalk.RunOnSave), you can set it up to run `import_sorter` automatically when a dart file is saved:
```json
// in your settings.json file, or in your Workspace's `settings` section
{
  "emeraldwalk.runonsave": {
    "commands": [
      {
        "match": "\\.dart$",
        "cmd": "import_sorter ${file}"
      }
    ]
  }
}
```