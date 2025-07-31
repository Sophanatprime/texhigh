Example of using `texhigh`.

## Compile example

Install [texhigh](https://github.com/Sophanatprime/texhigh-rs/releases) and make sure TeX can find `texhigh.sty` and `texhigh.prelude.ths`, then run
```bash
# you need to build the font database before building the example.
# it will build the database by itself,
# but you will get an error when you first build the example.
texhigh font build 
mkdir ./texhigh-cache
xelatex --shell-escape example
```
or
```
lualatex --shell-escape example
```

## Compile source3 with highlighting

Install [texhigh](https://github.com/Sophanatprime/texhigh-rs/releases) and make sure TeX can find `texhigh.sty` and `texhigh.prelude.ths`.

Put `source3.texhigh.toml` and the modified `l3doc.cls` in the directory of the source code of `source3` (including `source3.tex`, `source3body.tex` and all `l3*.dtx`s, you will not need to copy these files by setting environment variable `TEXINPUTS` to `;$TEXMF/doc/latex/l3kernel//;$TEXMF/source/latex/l3kernel//`), then run
```
xelatex/lualatex --shell-escape source3.tex
makeindex -s gind.ist -o source3.ind source3.idx
makeindex -s gglo.ist -o source3.gls source3.glo
xelatex/lualatex --shell-escape source3.tex
xelatex/lualatex --shell-escape source3.tex
```
It's about 10 minutes to finish compiling.
