## CSS Selectors
- CSS is a styling language
- The styles are in the following structure ``[SELECTOR] {[Styles], ...}``
- There are multiples ways to write a selector
	- Use the name of the html tag you want to select
	- Class Selector (Using . before the name)
	- ID selector (Using # before the name)
- Examples
	- ``div p { }:`` Selects all paragraphs under the div tag whether they are inside another tag or not
	- ``div > p { }:`` Selects all paragraphs that are immediate children of div
	- ``p.alpha.beta > div > span > a { }:`` Selects all anchors that are immediate children of SPAN which are immediate children of DIV which are immediate children of paragraphs (with classes alpha and beta)
	- ``.alpha .beta { }:`` All tags that have class "beta" and have a parent tag which has class "alpha"
## Box Model
- 