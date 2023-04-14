<h1 style="text-align: center;">/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ - Wait, What?</h1>
<h2 style="text-align: center;">RegEx:  Regular Expression – Email matching</h2>

Have you ever signed up for a website you really didn’t want to signup to with a fake email address that looked like “asdfhlkajlkdjf” only to have it rejected as an invalid email address?  That fancy bit of gobbledygook above is what made you craft a more reasonable noemail@nomail.com fake address instead.  

## Summary

In this tutorial, we are going to tell you what that gobbledygook actually means and does.  How it prevents you from just banging out several characters to get by the email requirement of the site you're on. 

Let's take a quick look at the code and begin to unpack it.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

+ / are your Boundaries
+ ^ and $ are your Anchors
+ () we use these to set the Groupings
+ [] deliminate the Bracket Expressions
+ Within the [] you'll have your charcter classes.
+ We use the \ as the Escaping character to print .'s.  

Let's see it inserted into a some JavaScript.

>function validateEmail(email)
>{  
>const regex = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;
>return regex.test(email);
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

Anchors are assertions about the engine's current position in the string.  In our email testing regex we are using `^` and `$`.  The ^ will assert the beginning of the regex and the `$` will assert the end.  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`.  Although it is technically a boundary, the forward slash / is used at the beginning and end of the string to denote its beginning and ending.

### Quantifiers

In our regex, we want to have at least 1 of each character class in groups 0 and 1.  It is the plus sign + after the closing ] at the end but before the group closing parenthesis ) that makes that happen.  
### Grouping Constructs

Within our code snipit we see three instances of grouping where the smaller groups are enclosed in parenthesis ().  Each one of these is assigned a group number starting at zero.  We use the groups to incorporate only the items we require for each unique section we are searching.  When we have multiple groups, we refer to them as subexpressions.

### Bracket Expressions

A bracket expression
### Character Classes

Character Classes refer to the items seperated within
### Flags
{2,6}
### Character Escapes

## Author

After running a successful E-Commerce platform for several years. 