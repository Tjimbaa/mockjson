# WebDev-RTE


<h5 align="center"><img width="300" src="https://github.com/Tjimbaa/mockjson/blob/main/umbraco_logo_white_1.png" alt="Umbraco logo">
  <p>This is a WYSIGYG Rich Text Editor built for Umbraco</p>
</h5>



## Table of Contents
* How to run the app
* How to use the RTE
* 123
* Features
* Future Features
* How to contribute
* What the prototype looks like

## How to run the app
1. Either a git client or downlaod the app and open the folder in the cli
2. Install all dependencies using the `npm install` command
3. Start the web server using the `npm run dev` command. The app will be served at http://localhost:3000/
4. Go to http://localhost:3000/ and get started

## How to use the RTE
There are three main UI components consisting of shortcutPanel, blockMenu, hoverMenu and input searching.
1. The shortcutPanel is placed on right side and gives an overview of all the shortcuts included in the RTE, and can be applied to text
2. The blockMenu is accessed by using the command ctrl + k, and the purpose of this is to build building blocks.
3. The hoverMenu is accessed when selecting / highlighting some text for styling, and includes the typical features on a RTE.

## Features

### getCommands
```
export interface EditorCommand {
  name: string;
  description: string;
  aliases: string[];
  keyboardShortcut: string[]
  command(): void
  icon: string;
  tags: string[];
}
``` 

**aliases** is a list of alternative names to commands, which makes the searching better. For example can bold have the alias heavy, when doing a search for heavy bold will appear.

**KeyboardShortcut** is an array of buttons that form a shortcut

**Command()** is a function which calls a specific editor command

**tags** is used to filter a list of **commands** based on which menu should display them.

### searchCommands
```
export const searchCommands = (
  search: string,
  tag?: string
): EditorCommand[] => {
  const filtered = getCommands().filter(
    x =>
      (x.name.toLocaleLowerCase().includes(search) ||
        x.aliases.some(y => y.includes(search))) &&
      (tag ? x.tags.some(z => z.includes(tag)) : true)
  );

  return filtered;
};
```

## Future Features
1. Documentation
2. Test
3. Customization
4. Table of Contents
5. Collaborative editing

## How to Contribute
1. Clone repo and create a new branch $ git checkout http:com/Tjimbaa/WebDev-RTE -b name for new branch
2. Make changes and test
3. Sumbit Pull Request with comprehensive description of changes

## What the prototype looks like
![Prototype image](https://github.com/Tjimbaa/mockjson/blob/main/rte.png)

## Why Use This RTE?
This RTE is easy to implement, and easy to install
* Takes a few seconds to setup
* Can be implemented with and without a framework
