# Naught

Based heavily on [The Web that Never Was -  Dylan Beattie](https://www.youtube.com/watch?v=8JOD1AQGqEg), with some differences
- 24:13 HTML naught
- 39:35 Hyper Lisp

## Syntax
Elements must have either attributes and/or contents to be valid naught syntax. `~<element>` is NOT valid syntax.
- `~<element>{contents}` HTML Element with no attributes, contents may be blank (`~<element>{}`)
- `~<element>(colon separated attributes)` Empty HTML element with attributes
- `~<element>(colon separated attributes){contents}` HTML Element with attributes

### New Special Entities
For putting code in `~pre` or `~code` use the following new entities:
- Tilde (`~`) use `&tilde;`
- Right curly brace (`}`) use `$rbrace;` ([reference](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references))

### Elements

### Example
```
~html(lang:en){
	~metadata{
		~title{It's HTML, Jim, but not as we know it...}
	}
	~script(type:text/javascript){
	}
	~body{
		~h1{Hello, World!}
		~p{
			Using HTML, we can make paragraphs, and even
			~a(href:grid!cern.ch/hello.html){link}
			to other documents into our paragraphs!
			~span(id:greeting-span)
		}
                ~pre{
                this is an &tilde;span{example$rbrace; that contains naught in preformatted text
                }
		~form(method: SUBMIT, id:main-form){
			~input(type:text){What's your name?}
			~input(type:button, action: submit){Go!}
		}
		~img(src:grid!cern.ch/images/test.jpg)
	}
}
```

## Transpiler
`$> naught input.nau`
### Instructions
TODO

### Similar Frameworks
- [pug](https://pugjs.org)
- [haml](https://haml.info) (PHP, ASP, and ERB)
- [slim](https://slim-template.github.io) (ruby)

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
