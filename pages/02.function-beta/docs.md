---
title: 'Example Page'
taxonomy:
    category:
        - API
        - Test
    tag:
        - API
---

Hello, David here. This CMS uses Markdown to style the documentation. You don't have to type Markdown, the editor has buttons for everything. Here are some examples of what you can do.

##Heading 2
This heading is used for major section within the article.

###Heading 3
Use this for all other subheadings.

Text formatting is easy you do **this for bold** and _this for itallics_ .You can add inline code for short snippets like this. `var codeExample = "hello";` If you want to add a standalone example you just indent it one tab. Make sure you leave one empty line above the code example.

	//yay code
	var code = 1;

## Tables are not a problem
|  Function name  |  Function value  |  Function second value  |
|  :------------  |  :------------:  |  --------------------:  |
|  Aligned left |  Aligned center  |  Aligned right   |
|  Function Z  |  123  |  112  |

## Notices
! Note this

!! Note this with some `$code`

!!! Note this **bold** thing

!!!! Separate notices with one empty line

## It supports tabs!
This is how you do it

[ui-tabs]
[ui-tab title="First Tab"]
Tabs can have any content in them including code.

	//yay code
	var code = 1;
[/ui-tab]
[ui-tab title="Second Tab"]
They can also have tables in them

|  Function name  |  Function value  |  Function second value  |
|  :------------  |  :-------------  |  :--------------------  |
|  Function X  |  223  |  445  |
|  Function Z  |  123  |  112  |

[/ui-tab]
[/ui-tabs]

Enjoy :)
