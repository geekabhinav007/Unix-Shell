# Regular Expressions

## What is Regular Expression?

- RE are used everywhere in DB validation, in Passwords, Emails everwhere RE is used.
- It all started in 1956 when HP was producing small terminals and Everything was in print.
- In 1972 First time Screen and Keyboard were Used Together.
- In 1956, Stephen Cole Kleene described a language called Regular Language. He has a Kleene theorem, Kleene paradox, Kleene's star and other 25-26 things having Kleene, his last name, before them all.
- If you don't know about Ken Thompson, search about him. He created an editor QED, (QED is line oriented computer text editor) where he used regex the first time
- Regular expressions are used in search engines, in search and replace dialogs of word processors and text editors, in text processing utilities such as `sed` and `AWK`, and in lexical analysis. Most general-purpose programming languages support regex capabilities either natively or via libraries, including Python, C, C++, Java, Rust, OCaml, and JavaScript.
- `grep`, Someone asked what is g and p stand for in `grep` if re stand  for regular expression. so here is the answer `Global search for Regular Expression and Print matching lines`.
- @rai sir please share your exprerience about `Edlin` and `ed`.
- Earlier We don't have personal Computer, so, Everone right program in notebook, correct them, then run on computer whenever get time, then check for any errors and get them running properly. According to experts, this is the best method to learn programming.

## Let's Start with regex.

Let's write our first Regex. Every string starting and ending by / is regex.
- When you say "*.txt" to a computer, you're matching all of the filenames that end in ".txt". The "*" matches any number of characters: it's a pattern.
- A warning before we go any further: the notation for regular expressions is ugly, even by the standards of programming.
- Regex Syntax `/pattern/option`
- we have multiple flags with regexp:
	- g = global
	- i = case insensitive / ignore case
	- m = multiline
	- s = single line
	- u = unicode
	- y = sticky
- What is caret Symbol?
- Group of characters are kept in () called groupers and are used when we want to match the exact string.
- 
## Character Classes

1. character set : `[abc]` it will match all character having a or b or c.
1. negated set : `[^abc]` match all chracter except a and b and c.
1. range : `[a-d]` Matches a character having a character code between the two specified characters inclusive.
1. dot : `.` Matches any character except linebreaks. Equivalent to `[^\n\r]`.
1. word : `\w` Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
1. not word : `\W` Matches any character that is not a word character (alphanumeric & underscore).
1. digit : `\d` Matches any digit character (0-9). Equivalent to [0-9].
1. not digit : `\D` Matches any character that is not a digit character (0-9). Equivalent to`[^0-9]`.
1. whitespace : `\s` Matches any whitespace character (spaces, tabs, line breaks).
1. not white space : `\S` Matches any character that is not a whitespace character (spaces, tabs, line breaks).

## Anchors 
1. begining : 
 
