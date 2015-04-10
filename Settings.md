# Editor Settings
Preferences -> Settings - User
change to:
```
{
    // "font_face": "consolas",
    "font_size": 11,
    "highlight_line": true,
    "tab_size": 4,
    "translate_tabs_to_spaces": true,
    "word_wrap": true
}
```

# Eclipse Style Shortcuts
Preferences -> Key Bindings - User
change to:
```
[
  { "keys": ["f12"], "command": "htmlprettify"},
  { "keys": ["f1"], "command": "fold" },
  { "keys": ["f2"], "command": "unfold" },
  { "keys": ["ctrl+l"], "command": "show_overlay", "args": {"overlay": "goto", "text": "@"} },
  
  { "keys": ["ctrl+space"], "command": "auto_complete" },
  { "keys": ["ctrl+space"], "command": "replace_completion_with_auto_complete", "context":
    [
      { "key": "last_command", "operator": "equal", "operand": "insert_best_completion" },
      { "key": "auto_complete_visible", "operator": "equal", "operand": false },
      { "key": "setting.tab_completion", "operator": "equal", "operand": true }
    ]
  },
  { "keys": ["ctrl+d"], "command": "run_macro_file", "args": {"file": "Packages/Default/Delete Line.sublime-macro"} },
  { "keys": ["ctrl+shift+c"], "command": "toggle_comment", "args": { "block": false } },
  { "keys": ["ctrl+shift+c"], "command": "toggle_comment", "args": { "block": true } },
  { "keys": ["ctrl+shift+f"], "command": "reindent" , "args": {"single_line": false}},
  { "keys": ["alt+up"], "command": "swap_line_up" },
  { "keys": ["alt+down"], "command": "swap_line_down" },
  { "keys": ["ctrl+alt+j"], "command": "join_lines" },
  { "keys": ["ctrl+alt+down"], "command": "duplicate_line" },
  { "keys": ["shift+ctrl+r"], "command": "show_overlay", "args": {"overlay": "goto", "show_files": true} },
  { "keys": ["ctrl+l"], "command": "show_overlay", "args": {"overlay": "goto", "text": ":"} },
  { "keys": ["shift+ctrl+f4"], "command": "close_all" },
  { "keys": ["shift+ctrl+y"], "command": "lower_case" },
  { "keys": ["shift+ctrl+x"], "command": "upper_case" }
]
```


# Install Package Control Plugin
1. Through the Sublime Text console: Ctrl+` shortcut or via View > Show Console.
2. Paste the following python code (for Sublime Text 3):

import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)


# Run java
Tools -> New Build System:
{
    "shell_cmd": "javac \"$file\"",
    "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
    "selector": "source.java",
    "encoding": "GBK",
    "variants":
        [{
            "name":"Run",
            "shell_cmd": "java \"$file_base_name\""
        }]
}
