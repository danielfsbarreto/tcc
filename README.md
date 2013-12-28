tcc
===

Projeto de conclusão de curso

Instalação do LaTeX no MacOS X
---------------------------------------------
Baixe e instale o arquivo MaTeX.pkg em http://tug.org/mactex/

Customização de scripts
---------------------------------
* nomencl

1 - Crie o arquivo Nomenclature.engine com o conteúdo:

`#!/bin/sh

bfname=$(dirname "$1")/"`basename "$1" .tex`"
makeindex "$bfname".nlo -s nomencl.ist -o "$bfname".nls`

2 - Salve-o no diretório `~/Library/TeXShop/Engines/Nomenclature.engine`

3 - Rode o comando `chmod u+x ~/Library/TeXShop/Engines/Nomenclature.engine` para torná-lo executável

4 - Reinicie o TeXShop

5 - O item Nomenclature estará no drop down próximo ao botão Typeset.

Pacotes extras
--------------------
* \usepackage{float}
Faz com que tabelas e figuras flutuem no documento
Ex.:
	\begin{table}[H]
		\centering
		\begin{tabular}
		\end{tabular}
	\end{table}

* \usepackage{nomencl}
Criação de lista de siglas
Ex.:
	\makenomenclature 						// Necessário no início do documento
	\nomenclature{XP}{eXtreme Programming} 	// Definição de sigla
	\renewcommand{\nomname}{Lista de Siglas}	// Customização do título da sessão de siglas
