|  No.  | [Reverse Program]                                                                  |
| :---: | -------------------------------------------------------------------------- |
|   1   | [Reverse String?](#Reverse-String)                                         |
|   2   | [Revers number?](#Revers-number)                                           |



### **Reverse String?**
```php
$s = 'mohit saxena';		
$l = strlen($s);
for($i=$l-1; $i>=0; $i--){
    echo $s[$i];
}

Output:- anexas tihom

--------------------------------------------------------------------
# 2 Option
$str = 'Mohit Saxena';
$length = strlen($str);

$rev = '';
for($i = $length-1; $i >= 0; $i--) {
    $rev .= $str[$i]; 
}
echo $rev;

Output:- anexaS tihoM
```
**[⬆ Back to Top](#table-of-contents)**

### **Revers number?**
```php
# Type 1st:-
$num = 2039;
$revnum = 0;
while ($num != 0){
    $revnum = $revnum * 10 + $num % 10;
    $num = (int)($num / 10); 
} 
echo "Reverse number: $revnum";

--------------------------------------------------------------------------
# Type 2nd:-

$num = 2314056;  
$revnum = 0;  
while ($num > 1){  
    $rem = $num % 10;  
    $revnum = ($revnum * 10) + $rem;  
    $num = (int)($num / 10);   
}  
echo "Reverse number of 23456 is: $revnum";  

Output:- Reverse number of 23456 is: 6504132
```
**[⬆ Back to Top](#table-of-contents)**
