Static code analysis
<!--more-->
# Python
https://luminousmen.com/post/python-static-analysis-tools

typings ?

## pylint 

check PEP8 and some errors
```
sudo apt-get install pylint
```
usage 

pylint <file/dir> --rcfile=<.pylintrc>


## flakes 

no style check , minimizes 
pip install --upgrade pyflakes

+ flake8 adds style checks 


## Mypy 
typings + static type checking 


## autopep8
pip install --upgrade autopep8


autopep8 --in-place -aa -p 2 -d <filename>

## prospector 


 pip install prospector

prospector --strictness high

```
 strictness: medium
test-warnings: true
doc-warnings: true
autodetect: false
max-line-length: 120

pep8:
    full: true
    disable:
      - N803 # argument name should be lowercase
      - N806 # variable in function should be lowercase
      - N812 # lowercase imported as non lowercase

pylint:
    run: true
    disable:
      - too-many-locals
      - arguments-differ
      - no-else-return
      - inconsistent-return-statements
      
pep257:
    run: true
    disable:
      - D203 # 1 blank line required before class docstring
      - D212 # Multi-line docstring summary should start at the first line
      - D213 # Multi-line docstring summary should start at the second line
```

# C++

https://hackernoon.com/why-you-should-really-care-about-c-c-static-analysis-db13f4463b2d
https://github.com/mre/awesome-static-analysis
http://cppcheck.sourceforge.net/demo/
https://github.com/khiguera/cppcheckTutorial

## cppcheck 

sudo apt-get install cppcheck

Install `linter`  and `linter-cppcheck` in atom. Restart `atom` install necessary dependencies from proposed pop message, restart.


1. run recursive check in current directory
```
 cppcheck . --enable=all --std=c++14 --verbose
```

2. 


cpplint

## CLANG ecosystem

install Clang
```
sudo apt-get install clang
```


clang analyzer 
clang tidy

gcc / clang compilation with all warnings, flags 


1. Code metrics
2. Dependencies
3. Immutability
4. Dead code
5. API breaking change
6. API usage


Create `compilation_database.json` - Clang style compile instructions list with all includes and env variables,
can be used to run `cppcheck` on `make`-projects 

install 

`pip install compiledb` 

1. run as wrapper 
```
compiledb make
```

2. run `no-build`
```
compiledb -n make
```



# pre-commit hooks 

https://github.com/pre-commit/demo-repo#readme
https://github.com/Ericsson/codechecker
https://github.com/mre/awesome-static-analysis#cc