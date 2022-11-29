# Regex

| Description                                                                    | Regex              |                                      | Output                                   |
| ------------------------------------------------------------------------------ | ------------------ | ------------------------------------ | ---------------------------------------- |
| Character                                                                      | curious            | I am curious                         | I am **curious**                         |
| Dot `.` : Any Character                                                        | .                  | abcd                                 | **a b c d**                              |
| Character Sets `[abc]` : Matches any of the specified                          | b\[ae]r            | bar ber bir bor bur                  | **bar** **ber** bir bor bur              |
| Negated Character Sets`[^abc]` : Matches except any of the specified           | b\[^eo]r           | bar ber bir bor bur                  | **bar** ber **bir** bor **bur**          |
| Letter Range`[a-z]` : Matches letters in the range (inclusive). Case-sensitive | \[e-o]             | abcdefghijklmnopqrstuvwxyz           | abcd**efghijklmno**pqrstuvwxyz           |
| Number Range`[0-9]` : Matches numbers in the range (inclusive)                 | \[3-6]             | 0123456789                           | 012**3456**789                           |
| Asterisk `*` : zero or more                                                    | be\*r              | br ber beer                          | **br ber beer**                          |
| Plus `+` : one or more                                                         | be+r               | br ber beer                          | br **ber beer**                          |
| Question mark `?` : Optional                                                   | colou?r            | color, colour                        | **color**, **colour**                    |
| Curly Braces `{n}` : n number of occurrences                                   | be{2}r             | ber beer beeer beeeer                | ber **beer** beeer beeeer                |
| Curly Braces `{n,}` : n or more number of occurrences                          | be{3,}r            | ber beer beeer beeeer                | ber beer **beeer beeeer**                |
| Curly Braces `{n,m}` :  between n and m number of occurrences                  | be{1,3}r           | ber beer beeer beeeer                | **ber beer beeer** beeeer                |
| Parentheses `( )`: Grouping                                                    | (haa)              | ha-ha,haa-haa                        | ha-ha,**haa**-**haa**                    |
| Referencing a Group `\n` : nth group                                           | (ha)-\1,(haa)-\2   | ha-ha,haa-haa                        | **ha-ha,haa-haa**                        |
| Parentheses `(?: )` : Non-capturing Grouping                                   | (?:ha)-ha,(haa)-\1 | ha-ha,haa-haa                        | **ha-ha,haa-haa**                        |
| Pipe Character `\|` :                                                          | (c\|r)at           | cat rat dog                          | **cat rat** dog                          |
| Escape Character `\`                                                           | (\\\*\|\\.)        | (\*) Asterisk.                       | (**\***) Asterisk**.**                   |
| Caret Sign `^` : Selecting by Line Start                                       | ^B                 | Basic                                | **B**asic                                |
| Dollar Sign `$` : Selecting by End of Line                                     | html$              | https://domain.com/what-is-html.html | https://domain.com/what-is-html.**html** |
| Word Character `\w` : Letter, Number and Underscore                            |                    |                                      |                                          |
| Except Word Character `\W`                                                     |                    |                                      |                                          |
| Number Character `\d`                                                          |                    |                                      |                                          |
| Except Number Character \D                                                     |                    |                                      |                                          |
| Space Character \s                                                             |                    |                                      |                                          |
| Except Space Character \S                                                      |                    |                                      |                                          |

