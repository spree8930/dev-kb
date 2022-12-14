# Regex

{% hint style="info" %}
[https://regexlearn.com](https://regexlearn.com/cheatsheet)
{% endhint %}

| Description                                                                    | Regex                                                     |                                      | Output                                   |
| ------------------------------------------------------------------------------ | --------------------------------------------------------- | ------------------------------------ | ---------------------------------------- |
| Character                                                                      | curious                                                   | I am curious                         | I am **curious**                         |
| Dot `.` : Any Character                                                        | .                                                         | abcd                                 | **a b c d**                              |
| Character Sets `[abc]` : Matches any of the specified                          | b\[ae]r                                                   | bar ber bir bor bur                  | **bar** **ber** bir bor bur              |
| Negated Character Sets`[^abc]` : Matches except any of the specified           | b\[^eo]r                                                  | bar ber bir bor bur                  | **bar** ber **bir** bor **bur**          |
| Letter Range`[a-z]` : Matches letters in the range (inclusive). Case-sensitive | \[e-o]                                                    | abcdefghijklmnopqrstuvwxyz           | abcd**efghijklmno**pqrstuvwxyz           |
| Number Range`[0-9]` : Matches numbers in the range (inclusive)                 | \[3-6]                                                    | 0123456789                           | 012**3456**789                           |
| Asterisk `*` : zero or more                                                    | be\*r                                                     | br ber beer                          | **br ber beer**                          |
| Plus `+` : one or more                                                         | be+r                                                      | br ber beer                          | br **ber beer**                          |
| Question mark `?` : Optional                                                   | colou?r                                                   | color, colour                        | **color**, **colour**                    |
| Curly Braces `{n}` : n number of occurrences                                   | be{2}r                                                    | ber beer beeer beeeer                | ber **beer** beeer beeeer                |
| Curly Braces `{n,}` : n or more number of occurrences                          | be{3,}r                                                   | ber beer beeer beeeer                | ber beer **beeer beeeer**                |
| Curly Braces `{n,m}` :  between n and m number of occurrences                  | be{1,3}r                                                  | ber beer beeer beeeer                | **ber beer beeer** beeeer                |
| Parentheses `( )`: Grouping                                                    | (haa)                                                     | ha-ha,haa-haa                        | ha-ha,**haa**-**haa**                    |
| Referencing a Group `\n` : nth group                                           | (ha)-\1,(haa)-\2                                          | ha-ha,haa-haa                        | **ha-ha,haa-haa**                        |
| Parentheses `(?: )` : Non-capturing Grouping                                   | (?:ha)-ha,(haa)-\1                                        | ha-ha,haa-haa                        | **ha-ha,haa-haa**                        |
| Pipe Character `\|` :                                                          | (c\|r)at                                                  | cat rat dog                          | **cat rat** dog                          |
| Escape Character `\`                                                           | (\\\*\|\\.)                                               | (\*) Asterisk.                       | (**\***) Asterisk**.**                   |
| Caret Sign `^` : Selecting by Line Start                                       | ^B                                                        | Basic                                | **B**asic                                |
| Dollar Sign `$` : Selecting by End of Line                                     | html$                                                     | https://domain.com/what-is-html.html | https://domain.com/what-is-html.**html** |
| Word Character `\w` : Letter, Number and Underscore                            |                                                           |                                      |                                          |
| Except Word Character `\W`                                                     |                                                           |                                      |                                          |
| Number Character `\d`                                                          |                                                           |                                      |                                          |
| Except Number Character `\D`                                                   |                                                           |                                      |                                          |
| Space Character `\s`                                                           |                                                           |                                      |                                          |
| Except Space Character `\S`                                                    |                                                           |                                      |                                          |
| Positive Lookahead: `(?=)`                                                     | <p>\d+(?=PM)<br><br>Any number followed by PM</p>         | Date: 4 Aug 3PM                      | Date: 4 Aug **3**PM                      |
| Negative Lookahead: `(?!)`                                                     | <p>\d+(?!PM)<br><br>Any number not followed by PM</p>     | Date: 4 Aug 3PM                      | Date: **4** Aug 3PM                      |
| Positive Lookbehind: `(?<=)`                                                   | <p>(?&#x3C;=\$)\d+<br><br>Any number preceded by $</p>    | Product Code: 1064 Price: $5         | Product Code: 1064 Price: $**5**         |
| Negative Lookbehind: `(?<!)`                                                   | <p>(?&#x3C;!$)\d+<br><br>Any number not preceded by $</p> | Product Code: 1064 Price: $5         | Product Code: **1064** Price: $5         |
| Global Flag `/g` : Selects all matches                                         |                                                           |                                      |                                          |
| Multiline Flag `/m` : Handles each line separately                             |                                                           |                                      |                                          |
| Case insensitive Flag `/i`                                                     |                                                           |                                      |                                          |

