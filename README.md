# Тънки капилярни мостове с цилиндрична симетрия
Резпозитория за дипломната работа на Васил Иванов, ФХФ

#За компилиране на документа


Компилира с XeLaTeX + MikTeX + Bibtex, като стандартно рецептата е xelatex → bibtex → xelatex → xelatex 
Нужните шрифтове и снимки са в репозиторията.

За най-просто: 
VS Code с extension-a [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) + предварително изтеглен [MiKTeX](https://miktex.org/), който автоматично се грижи за всички latex пакети в документа.

VS Code settings.json за да тръгва с xelatex:
```javascript
{
	"latex-workshop.latex.tools": [
		{
			"name": "xelatex",
			"command": "xelatex",
			"args": [
				"-synctex=1",
				"-interaction=nonstopmode",
				"-file-line-error",
				"%DOC%"
			]
		},
		{
			"name": "biber",
			"command": "biber",
			"args": [
				"%DOCFILE%"
			]
		}
	],
	"latex-workshop.latex.recipes": [
		{
			"name": "xelatex -> biber -> xelatex*2",
			"tools": [
				"xelatex",
				"biber",
				"xelatex",
				"xelatex"
			]
		}
	],
    "files.exclude": {
        "**/_minted-*": true,
        "**/*.aux": true,
        "**/*.bbl": true,
        "**/*.blg": true,
        "**/*.lof": true,
        "**/*.log": true,
        "**/*.lol": true,
        "**/*.lot": true,
        "**/*.nav": true,
        "**/*.out": true,
        "**/*.snm": true,
        "**/*.swp": true,
        "**/*.toc": true,
        "**/*.vrb": true
	},


}
```
