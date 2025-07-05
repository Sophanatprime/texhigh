Example of using `texhigh`.

## Compile example

Install [texhigh](https://github.com/Sophanatprime/texhigh-rs/releases) and make sure TeX can find `texhigh.sty` and `texhigh.prelude.ths`, then run
```
xelatex --shell-escape example
```
or
```
lualatex --shell-escape example
```

## Compile source3 with highlighting

Install [texhigh](https://github.com/Sophanatprime/texhigh-rs/releases) and make sure TeX can find `texhigh.sty` and `texhigh.prelude.ths`.

Put `source3.texhigh.toml` and the modified `l3doc.cls` in the directory of the source code of `source3` (including `source3.tex`, `source3body.tex` and all `l3*.dtx`s), then run
```
xelatex/lualatex --shell-escape source3.tex
makeindex -s gind.ist -o source3.ind source3.idx
makeindex -s gglo.ist -o source3.gls source3.glo
xelatex/lualatex --shell-escape source3.tex
xelatex/lualatex --shell-escape source3.tex
```
It's about 10 minutes to finish compiling. You may need to increase the `pool_size`.
