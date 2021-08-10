# check_http_content_equals

Nagios plugin that will check a website and compares the content to a specified string or file.

[![License](https://img.shields.io/badge/license-GPLv3-408576.svg)](https://www.gnu.org/licenses/)
[![Type](https://img.shields.io/badge/type-%2Fbin%2Fbash-red.svg)](https://en.wikipedia.org/wiki/Bash_(Unix_shell))
---

## 1. Usage
```shell
Usage:  check_http_content_equals --url <string> --compare-to <string> [--compare-to-file <string>] [--ua <string>] [--cookie <data> [--cookie <data>]]
OR      check_http_content_equals --help
OR      check_http_content_equals --version
```

## 2. Examples

### 2.1 Compare to specified string with custom user-agent

````shell
> check_http_content_equals --url "https://blog.fefe.de/?ts=b5ff0762" --compare-to "$(cat example_compare.txt)" --ua "curl/7.37.0"   
[OK] Content matches!
Url:           https://blog.fefe.de/?ts=b5ff0762
----------------------------------------
Diff:
````

### 2.2 Compare to content of a specified file

````shell
> check_http_content_equals --url "https://blog.fefe.de/?ts=b5ff0762" --compare-to-file "example_compare.txt"   
[OK] Content matches!
Url:           https://blog.fefe.de/?ts=b5ff0762
----------------------------------------
Diff:
````

### 2.3 Compare to content of a specified file and set custom cookie

````shell
> check_http_content_equals --url "https://blog.fefe.de/?ts=b5ff0762" --compare-to-file "example_compare.txt" --cookie "css=fefe.css"   
[OK] Content matches!
Url:           https://blog.fefe.de/?ts=b5ff0762
----------------------------------------
Diff:
````
