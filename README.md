[![Build Status](https://mssqltools.visualstudio.com/CrossPlatBuildScripts/_apis/build/status/VSCode-MSSQL?branchName=main)](https://mssqltools.visualstudio.com/CrossPlatBuildScripts/_build/latest?definitionId=70&branchName=main)
[![Gitter](https://img.shields.io/badge/chat-on%20gitter-blue.svg)](https://gitter.im/Microsoft/mssql)

# mssql for Visual Studio Code

Welcome to **mssql** for Visual Studio Code! An extension for developing Microsoft SQL Server, Azure SQL Database and SQL Data Warehouse everywhere with a rich set of functionalities, including:

- Connect to Microsoft SQL Server, Azure SQL Database and SQL Data Warehouses.
- Create and manage connection profiles and most recently used connections.
- Write T-SQL script with IntelliSense, Go to Definition, T-SQL snippets, syntax colorizations, T-SQL error validations and `GO` batch separator.
- Execute your scripts and view results in a simple to use grid.
- Save the result to json or csv file format and view in the editor.
- Customizable extension options including command shortcuts and more.

See [the mssql extension tutorial] for the step by step guide.

See [the SQL developer tutorial] to develop an app with C#, Java, Node.js, PHP, Python and R with SQL Server databases.

<img src="https://github.com/Microsoft/vscode-mssql/raw/main/images/mssql-demo.gif" alt="demo" style="width:480px;"/>

## Using

- First, install [Visual Studio Code] then install **mssql** extension by pressing **F1** or **ctrl+shift+p** to open command palette, select **Install Extension** and type **mssql**.
  - For macOS, you will need to install OpenSSL. Follow the install pre-requisite steps from [DotNet Core instructions].
- Open an existing file with a .sql file extension or open a new text file (**ctrl+n**) and change the language mode to SQL by pressing **ctrl+k,m** and select **SQL**. **mssql** commands and functionalities are enabled in the SQL language mode in Visual Studio Code editor.
- Create a new connection profile using command palette by pressing **F1**, type **sqlman** to run **MS SQL: Manage Connection Profile** command. Select **Create**. See [manage connection profiles] for more information about how to create and edit connection profiles in your User Settings (settings.json) file.
- Connect to a database by pressing **F1** and type **sqlcon** to run **MS SQL: Connect** command, then select a connection profile. You can also use a shortcut (**ctrl+shift+c**).
- Write T-SQL script in the editor using IntelliSense and Snippets. Type **sql** in the editor to list T-SQL Snippets.
- Execute T-SQL script or selection of statements in the script by pressing **F1** and type **sqlex** to run **MS SQL: Execute Query** command. You can also use a shortcut (**ctrl+shift+e**). See [customize shortcuts] to learn about change shortcut key bindings to **mssql** commands.
- View the T-SQL script execution results and messages in result view.

## Commands

The extension provides several commands in the Command Palette for working with `.sql` files:

- **MS SQL: Connect** to SQL Server, Azure SQL Database or SQL Data Warehouse using connection profiles or recent connections.
  - **Create Connection Profile** to create a new connection profile and connect.
- **MS SQL: Disconnect** from SQL Server, Azure SQL Database or SQL Data Warehouse in the editor session.
- **MS SQL: Use Database** to switch the database connection to another database within the same connected server in the editor session.
- **MS SQL: Execute Query** script, T-SQL statements or batches in the editor.
- **MS SQL: Cancel Query** execution in progress in the editor session.
- **MS SQL: Manage Connection Profiles**
  - **Create** a new connection profile using command palette's step-by-step UI guide.
  - **Edit** user settings file (settings.json) in the editor to manually create, edit or remove connection profiles.
  - **Remove** an existing connection profile using command palette's step-by-step UI guide.
  - **Clear Recent Connection List** to clear the history of recent connections.

## Options

The following Visual Studio Code settings are available for the mssql extension. These can be set in user preferences (cmd+,) or workspace settings `(.vscode/settings.json)`.
See [customize options] and [manage connection profiles] for more details.

```javascript
{
    "mssql.maxRecentConnections": 5,
    "mssql.connections":[],
    "mssql.shortcuts": {
        "event.toggleResultPane": "ctrl+alt+r",
        "event.toggleMessagePane": "ctrl+alt+y",
        "event.prevGrid": "ctrl+up",
        "event.nextGrid": "ctrl+down",
        "event.copySelection": "ctrl+c",
        "event.maximizeGrid": "",
        "event.selectAll": "",
        "event.saveAsJSON": "",
        "event.saveAsCSV": "",
        "event.saveAsExcel": ""
    },
    "mssql.messagesDefaultOpen": true,
    "mssql.logDebugInfo": false,
    "mssql.saveAsCsv.includeHeaders": true,
    "mssql.saveAsCsv.delimiter": ",",
    "mssql.saveAsCsv.lineSeparator": null,
    "mssql.saveAsCsv.textIdentifier": "\"",
    "mssql.saveAsCsv.encoding": "utf-8",
    "mssql.intelliSense.enableIntelliSense": true,
    "mssql.intelliSense.enableErrorChecking": true,
    "mssql.intelliSense.enableSuggestions": true,
    "mssql.intelliSense.enableQuickInfo": true,
    "mssql.intelliSense.lowerCaseSuggestions": false,
    "mssql.resultsFontFamily": "-apple-system,BlinkMacSystemFont,Segoe WPC,Segoe UI,HelveticaNeue-Light,Ubuntu,Droid Sans,sans-serif",
    "mssql.resultsFontSize": 13,
    "mssql.copyIncludeHeaders": false,
    "mssql.copyRemoveNewLine" : true,
    "mssql.splitPaneSelection": "next",
    "mssql.format.alignColumnDefinitionsInColumns": false,
    "mssql.format.datatypeCasing": "none",
    "mssql.format.keywordCasing": "none",
    "mssql.format.placeCommasBeforeNextStatement": false,
    "mssql.format.placeSelectStatementReferencesOnNewLine": false,
    "mssql.applyLocalization": false,
    "mssql.query.displayBitAsNumber": true,
    "mssql.persistQueryResultTabs": false
}
```
