<h1 style="text-align: center;">/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ - Wait, What?</h1>
<h2 style="text-align: center;">RegEx:  Regular Expression – Email Matching</h2>

Have you ever signed up for a website you really didn’t want to signup to with a fake email address that looked like “asdfhlkajlkdjf” only to have it rejected as an invalid email address?  That fancy bit of gobbledygook above is what made you craft a more reasonable noemail@nomail.com fake address instead.  

## Summary

In this tutorial, we are going to tell you what that gobbledygook actually means and does.  In addition, we'll look at how it prevents you from just banging out several characters to get by the email requirement of the site you're on. 

Let's take a quick look at the code and begin to unpack it.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

+ / are your Boundaries
+ ^ and $ are your Anchors
+ ( ) we use these to set the Groupings
+ `[ ]` deliminate the Bracket Expressions
+ Within the [ ] you'll have your charcter classes.
+ We use the \ as the Escaping character to print .'s.  

Let's see it inserted into a some JavaScript.

>function validateEmail(email)<br>
>{<br>
>const regex = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;<br>
>return regex.test(email);<br>
>}

This function will return either a TRUE or FALSE after it uses the TEST method to examine the pattern of the email inputted by the user.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors are assertions about the engine's current position in the string.  In our email testing regex we are using `^` and `$`.  The `^` will assert the beginning of the regex and the `$` will assert the end.  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`.  Although it is technically a boundary, the forward slash / is used at the beginning and end of the string to denote its beginning and ending.

### Quantifiers

In our regex, we want to have at least 1 of each character class in groups 0 and 1.  It is the plus sign + after the closing ] at the end but before the group closing parenthesis ) that makes that happen.  
### Grouping Constructs

Within our code snippit we see three instances of grouping where the smaller groups are enclosed in parenthesis ( ).  Each one of these is assigned a group number starting at zero.  We use the groups to incorporate only the items we require for each unique section we are searching.  When we have multiple groups, we refer to them as subexpressions.

### Bracket Expressions

Brackets [ ] designate a set of charcters to match. In our example, we see three sets of search criteria in brackets.  We can also tell it not to find these same items by writing the search by using the ^ to begin the string (/[^a-z]/) telling it not to find lowercase letters from a to z.   

See the carcter classes to see how they are used.
### Character Classes

Character Classes refer to the items seperated within the brackets [ ].  Let's look at each one in our example.
+ `[a-z0-9_\.-]`:  matches any lowercase letter, digit, underscore, dot. or hyphen character.
+ `[\da-z\.-]`:  matches any digit, lowercase letter, dot, or hyphen character.
+ `[a-z\.]{2,6}`:  matches any lowercase letter or dot character, repeated between 2 and 6 times.  
### Character Escapes

According to Wikipedia; "In computing and telecommunication, an escape character is a character that invokes an alternative interpretation on the following characters in a character sequence. An escape character is a particular case of metacharacters."

We have a few examples of escaped characters in our example:
+ `\d`: matches any digit character, equivalent to the character class [0-9].
+ `\.`: matches a literal dot character.

Both character escapes are used inside square brackets ([ ]) to create character classes that match specific sets of characters. `\d` is used in the character class [\da-z\.-] to match digits, and `\.` is used in the last part of the regular expression to match a literal dot character in the TLD (top level domain).

In addition, there's also a backslash escape `(\)` before the hyphen character (-) in the first two character classes: [a-z0-9_\.-] and [\da-z\.-]. This is because the hyphen character has a special meaning inside square brackets, where it is used to define a range of characters. In our examples above, 'a-z' can be spoken as "a to z"; however, the hyphen after the escape refers to the literal dash - character.  Therfore, it is treated as a literal character and included in the character class.
## Author


With a distinguished career in Sales and Management and an known talent for computers, I was asked to lead my company's new online department.  After a long online career where I learned a lot about Ecommerce and ux, I have now embarked on journey to make the applications and websites people use.  Visit my repo on Github at [dirtydenny](https://github.com/dirtydenny/).  If you’d like to add to this repo or contact me directly please email me at dallen7@socal.rr.com.