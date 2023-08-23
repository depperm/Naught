# Naught

Based heavily on [The Web that Never Was -  Dylan Beattie](https://www.youtube.com/watch?v=8JOD1AQGqEg), with some differences
- 24:13 HTML naught
- 39:35 Hyper Lisp

## Syntax
- `~<element>{contents}` HTML Element with no attributes
- `~<element>(colon separated attributes)` Empty HTML element
- `~<element>(colon separated attributes){contents}` HTML Element with attributes

### Elements

### Example
```
~html(lang:en){
	~metadata{
		~title{It's HTML, Jim, but not as we know it...}
	}
	~script(lang:js){
	}
	~body{
		~h1{Hello, World!}
		~p{
			Using HTML, we can make paragraphs, and even
			~a(href:grid!cern.ch/hello.html){link}
			to other documents into our paragraphs!
			~span(id:greeting-span)
		}
		~form(method: SUBMIT, id:main-form){
			~input(type:text){What's your name?}
			~input(type:button, action: submit){Go!}
		}
		~img(src:grid!cern.ch/images/test.jpg){Test Image}
	}
}
```

## Transpiler
TODO
### Instructions
TODO

### References
- [pug](pugjs.org)
- [haml](https://haml.info)
- [slim](https://slim-template.github.io)

## TODO
- Flesh out syntax
- Parser, find cross OS lang:
  - nim ([lexer](https://nim-lang.org/docs/compiler/lexer.html), [parser](https://nim-lang.org/docs/compiler/parser.html))?
  - go?
  - rust ([logos](https://github.com/maciejhirsz/logos), [pest](https://github.com/pest-parser/pest))?)
- Transpiler
- Example Project
- Live transpilation

### Wishlist
- Integrated SASS->auto compiles into css
- Get language accepted to not need Transpiler
- Integrate LaTeX? ([mathjax](https://www.mathjax.org) or [jslatex](http://blog.dreasgrech.com/2009/12/jslatex-jquery-plugin-to-directly-embed.html))
