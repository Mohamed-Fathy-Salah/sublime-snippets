these snippets are repeated code snippets used in competitive programming
## just put these files in 
### linux
`~/.config/sublime-text-3/Packages/User`

## installed packages on sublime
  ```
  PackageResourceViewer
  ```
#### C++
  ```
    Clang Format
    CppFastOlympicCoding (vvi,pii and so on)
    EasyClangComplete ( you have to install clang on ur machine)
    SublimeAStyleFormatter (`ctrl` + `alt` + `f` will format and indent ur code)
    SublimeGDB ( `ctrl`+`f5` for debugging )
  ```
## enable vintage mode (vi mod)
open `preferences` -> `settings` and modify the file with the following
  ```
    "ignored_packages":
	  [
	  ],
	  "vintage_start_in_command_mode": true
  ```
  
## compile and run
press `ctrl` + `p` -> `PackageResourceViewer: OpenResource` -> `c++` -> `c++ Single File.sublime-bulid`
if you want to use the internal terminal of sublime
  ```
  {
    "shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\"",
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c++",

    "variants":
    [
      {
        "name": "Run",
        "shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\""
      }
    ]
  }
  ```
  if you want to use ur system terminal (mine is `gnome-terminal` and i am using `bash` change them if u use other tools)
  ```
  {
    "cmd": ["g++","-g" ,"$file", "-o", "${file_path}/${file_base_name}"],
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c, source.c++, source.cxx, source.cpp",
    "variants":
    [
        {
            "name": "Run",
            "shell": true,
            "cmd": ["gnome-terminal -e 'bash -c \"${file_path}/${file_base_name};echo;echo;  echo Press ENTER to continue; read line;exit; exec bash\"'"]
        }
    ]    
  }
  ```
