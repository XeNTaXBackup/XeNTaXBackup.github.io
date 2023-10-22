## Post #1
- Username: ExcaliburZero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 22, 2021 12:49 am
- Post datetime: 2021-05-21T17:52:55+00:00
- Post Title: QuickBMS VSCode extension

I recently created a Visual Studio Code extension to add some language support for QuickBMS script files. It adds syntax highlighting and a few language features (ex. hover documentation for commands, go to definitions and references for functions, etc.).

The syntax highlighting supports most commands and keywords, but is still a work in progress. The hover documentation feature currently works for only a few commands, but I'm working on adding support for more.

Currently the extension works fully on Windows and Linux. On Mac it should support syntax highlighting, but does not yet support other language features ([but may eventually](https://github.com/ExcaliburZero/quickbms-lsp/issues/9)).

Screenshots




Installation
To install the language server, you can search "QuickBMS" in the extensions window in Visual Studio Code and click on and install the extension.


Technical details
The VS Code extension is written in Typescript and leverages a QuickBMS language server to support several language features.

The language server is written in Rust and uses the tree-sitter parser generator library to handle parsing. Since it is a language server, if someone wanted to create a QuickBMS extension for a different editor or IDE they might be able to leverage the language server.

More information on the extension and language servers can be found on their GitHub repositories (see Links section).


Versions / Changelog

 VS Code extension: https://github.com/ExcaliburZero/quickb ... ANGELOG.md
 Language server: https://github.com/ExcaliburZero/quickb ... ANGELOG.md

Links

 VS Code extension
    
 Marketplace page: https://marketplace.visualstudio.com/it ... o.quickbms
 GitHub repository: https://github.com/ExcaliburZero/quickbms_vscode

 Language server
    
 Crates.io package: https://crates.io/crates/quickbms-lsp
 GitHub repository: https://github.com/ExcaliburZero/quickbms-lsp
## Post #2
- Username: segabit
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 21, 2016 3:05 am
- Post datetime: 2022-12-23T03:14:17+00:00
- Post Title: QuickBMS VSCode extension

Thank you so much for sharing this. It's a really cool contribution. As a beginner in QuickBMS, I need this kind of subtle guidance, and I'm sure when I get more proficient, I'll want this as a time saver.
