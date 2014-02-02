TCC
===

Minha monografia

# Instalação do LaTeX no MacOS X
Baixe e instale o arquivo MacTeX.pkg em http://tug.org/mactex/

Baixe e instale o texmaker em http://www.xm1math.net/texmaker/download.html

#Customização de scripts
nomencl
-------

Para configurar a compilação utilizando o TeXmaker, basta modificar o comando utilizado para rodar o makeindex `"/usr/texbin/makeindex" %.nlo -s nomencl.ist -o %.nls`

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
\renewcommand{\nomname}{Lista de Siglas} % Customização do título da sessão de siglas
\printnomenclature

\nomenclature{XP}{eXtreme Programming} % Definição de sigla
```

#Tips and Tricks
Conversão de imagens
--------------------
`convert temp.png -compress lzw eps2:temp.eps`

ou

`convert temp.jpg -compress jpeg eps2:temp.eps`
