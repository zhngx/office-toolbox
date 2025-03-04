
# office-toolbox

Office-Toolbox is a set of tools for validating, and sideloading an Office Add-in. It is not (yet) a part of the official Office Add-in toolchain, but allows you to bypass the manual steps for sideloading add-ins. If you prefer to use the official Office toolchain, see our documentation on [getting started with Office Add-ins](https://dev.office.com/docs/add-ins/get-started/create-an-office-add-in-using-any-editor) and [how to sideload an add-in](https://dev.office.com/docs/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).

## Installation
> **Important:** If this is the first time you're using this tool, first install [Node.js](https://nodejs.org). For developers on Mac, we recommend using [Node Version Manager](https://github.com/creationix/nvm) to install Node.js with the right permissions. When the installation completes, restart your console (or if you are using Windows, restart your machine) to ensure you use the updated system environment variables.

Install `office-toolbox` globally using [NPM](http://npmjs.org/):
```bash
npm install -g office-toolbox
```

## Usage
You can supply arguments on the command-line:

```bash
$ office-toolbox sideload -m my-office-addin-manifest.xml -a word
```

Alternatively, you can run the tool without arguments and it will prompt you for information.

```bash
$ office-toolbox
```

## Validating an Office Add-in
```bash
$ office-toolbox validate
```

This tool validates the XML manifest for submission to the Office Store, using an online system, and displays the result in the terminal. 

If you created the manifest using the generator, it does not contain a support URL; you will be able to sideload the manifest locally, but you will need to provide a support URL before submitting it to the Office Store.

## Sideloading an Office Add-in
Before you submit your Office Add-in to the store, you should test it locally by sideloading its manifest. Be sure that the website is running, and then run the tool.

```bash
$ office-toolbox sideload
```

The tool validates the manifest against the online system. On Windows, the tool writes a registry key to HKEY\_CURRENT\_USER\Software\Microsoft\Office\16.0\WEF\Developer. On Mac, the tool creates a hard link in ~/Library/Containers/com.microsoft.Word/Data/Documents/wef to your manifest. The tool then generates a document, spreadsheet, or presentation containing your Office Add-in, which you can open every time you want to load your Add-in.

Copyright (c) 2018 Microsoft Corporation. All rights reserved.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

