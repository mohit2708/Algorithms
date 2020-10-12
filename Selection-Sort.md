# Selection Sort


![1](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_1.jpg)
![2](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_2.jpg)
![3](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_3.jpg)
![4](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_4.jpg)
![5](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_5.jpg)
![6](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_6.jpg)
![7](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/selection_sort_7.jpg)
```php
<?php 
function selection_sort(&$arr, $n)  
{ 
    for($i = 0; $i < $n ; $i++) 
    { 
        $low = $i; 
        for($j = $i + 1; $j < $n ; $j++) 
        { 
            if ($arr[$j] < $arr[$low]) 
            { 
                $low = $j; 
            } 
        } 
          
        // swap the minimum value to $ith node 
        if ($arr[$i] > $arr[$low]) 
        { 
            $tmp = $arr[$i]; 
            $arr[$i] = $arr[$low]; 
            $arr[$low] = $tmp; 
        } 
    } 
} 

$arr = array(64, 25, 12, 22, 11); 
$len = count($arr); 
selection_sort($arr, $len); 
echo "Sorted array : \n";  
  
for ($i = 0; $i < $len; $i++)  
    echo $arr[$i] . " ";   
?> 
```

