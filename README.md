# WebDev-RTE
RTE is a blabla 
![alt text][logo]

[logo]: https://umbraco.com/media/4mzda5do/umbraco_logo_blue05.png?quality=80 "Logo Title Text 1"

## Table of Contents
* 123
* 1234
* 12345
* 123456
* 1234567

## How to run the app
1. Either fork or downlaod the app and open the folder in the cli
2. Install all dependencies using the `npm i` command
3. Start the webs server using the `npm run dev` command. The app will be served at http://localhost:3000/
4. Go to http://localhost:3000/ and get started

## How to use the RTE
There are three main UI components consisting of shortcutPanel, blockMenu, hoverMenu and input searching.
1. The shortcutPanel is placed on right side and gives an overview of all the shortcuts included in the RTE, and can be applied to text
2. The blockMenu is accessed by using the comamnd ctrl + k, and the purpose of this is to build building blocks.
3. The hoverMenu is accessed when selecting some text for styling, and includes the typical features on a RTE.

## User Stories
* A user can create content using different menus

## Features

## Installation
You don't need any frameworks to work with the prototype. It can be installed by running the following commands

```
npm install
```

## Development
To run the program you need to run the follow command, which can be found under package.json file in the script tag.

```
npm run dev
```

## Introduction
Looking at the UI component it consist of three main components - which is the hoverMenu, shortcutPanel, and blockMenu

## You think you've found a bug?
We want to fix it ASAP! But before fixing a bug we need to reproduce and confirm it.
We ask you to respect two things:
* fill the GitHub issue template by providing the bug description and appropriate versions

## Components 

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

### seachCommands
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

## Why Use This RTE?
This RTE is easy to implement, and easy to install
* Takes a few seconds to setup
* Can be implemented with and without a framework
