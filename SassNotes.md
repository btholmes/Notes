# Notes about Sass
	[Info Link](http://sass-lang.com/guide)
	1. It uses preprocessing, so we can create variables and do nesting and stuff. 
	2. $variable: 100px; 
	3. Then call it with height: $variable; (Or whatever you want to attach it to)
	4. Can import script at the top, and it it will be loaded after the existing scss in the page
	5. @import 'page.scss'; 
	6.) Use @mixin name($param){ }  and @include name(value); to save time writing 
	7.) Also can do inheritance with @extend className;  