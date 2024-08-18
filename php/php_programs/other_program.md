|  No.  | Other Programs                                                                  |
| :---: | -------------------------------------------------------------------------- |
|   1   | [Match the Two words same or not?](#match-the-two-words-same-or-not)           |

### Match the Two words same or not
```php
function matchSortedWords($word1, $word2) {
    // Convert both words to arrays of characters
    $arr1 = str_split($word1);
    $arr2 = str_split($word2);
    // Sort the arrays
    sort($arr1);
    sort($arr2);

    // Convert arrays back to strings
    $sortedWord1 = implode('', $arr1);
    $sortedWord2 = implode('', $arr2);

    // Compare the sorted versions of both words
    if ($sortedWord1 === $sortedWord2) {
        echo "$word1 and $word2 are the same after sorting.\n";
    } else {
        echo "$word1 and $word2 are not the same after sorting.\n";
    }
}

// Words to be compared
$word1 = 'mohit';
$word2 = 'hoimt';

// Call the function to compare
matchSortedWords($word1, $word2);

Output:- mohit and hoimt are the same after sorting.
```
**[⬆ Back to Top](#table-of-contents)**