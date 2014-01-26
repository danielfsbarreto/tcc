TCC
===

Minha monografia

# Instalação do LaTeX no MacOS X
Baixe e instale o arquivo MaTeX.pkg em http://tug.org/mactex/

#Customização de scripts
nomencl
-------

1 - Crie o arquivo `Nomenclature.engine` com o conteúdo:
```bash
#!/bin/sh

bfname=$(dirname "$1")/"`basename "$1" .tex`"
makeindex "$bfname".nlo -s nomencl.ist -o "$bfname".nls
```

2 - Salve-o no diretório `~/Library/TeXShop/Engines/Nomenclature.engine`

3 - Rode o comando `chmod u+x ~/Library/TeXShop/Engines/Nomenclature.engine` para torná-lo executável

4 - Reinicie o TeXShop

5 - O item Nomenclature estará no drop down próximo ao botão Typeset.

Obs.: Para configurar a compilação utilizando o TeXmaker, basta modificar o comando utilizado para rodar o makeindex `"/usr/texbin/makeindex" %.nlo -s nomencl.ist -o %.nls`

#Pacotes extras
\usepackage{float}
------------------
Faz com que tabelas e figuras flutuem no documento.

Ex.:
```LaTeX
\begin{table}[H] % Usar o parâmetro H (here)
	\centering
	\begin{tabular}
	\end{tabular}
\end{table}
```
\usepackage{nomencl}
--------------------
Criação de lista de siglas.

Ex.:
```LaTeX
\makenomenclature % Necessário no início do documento
\nomenclature{XP}{eXtreme Programming} % Definição de sigla
\renewcommand{\nomname}{Lista de Siglas} % Customização do título da sessão de siglas
```

#Tips and Tricks
Conversão de imagens
--------------------
Como comverter imagens `.jpeg` ou `.png` para `.eps`? Muito simples!
`convert temp.png -compress lzw eps2:temp.eps`
ou
`convert temp.jpg -compress jpeg eps2:temp.eps`
