# Bubble Sort

#### Example-1:
![bubble-sort](https://github.com/mohit2708/Algorithms/blob/Sorting-Algorthims/img/Bubble-sort.gif)

#### Example-2:
__First Pass:__<br>
( __5 1__ 4 2 8 ) –> ( __1 5__ 4 2 8 ), Here, algorithm compares the first two elements, and swaps since 5 > 1.<br>
( 1 __5 4__ 2 8 ) –>  ( 1 __4 5__ 2 8 ), Swap since 5 > 4<br>
( 1 4 __5 2__ 8 ) –>  ( 1 4 __2 5__ 8 ), Swap since 5 > 2<br>
( 1 4 2 __5 8__ ) –> ( 1 4 2 __5 8__ ), Now, since these elements are already in order (8 > 5), algorithm does not swap them.<br>

__Second Pass:__<br>
( __1 4__ 2 5 8 ) –> ( __1 4__ 2 5 8 )<br>
( 1 __4 2__ 5 8 ) –> ( 1 __2 4__ 5 8 ), Swap since 4 > 2<br>
( 1 2 __4 5__ 8 ) –> ( 1 2 __4 5__ 8 )<br>
( 1 2 4 __5 8__ ) –>  ( 1 2 4 __5 8__ )<br>
Now, the array is already sorted, but our algorithm does not know if it is completed. The algorithm needs one whole pass without any swap to know it is sorted.<br>

__Third Pass:__<br>
( __1 2__ 4 5 8 ) –> ( __1 2__ 4 5 8 )<br>
( 1 __2 4__ 5 8 ) –> ( 1 __2 4__ 5 8 )<br>
( 1 2 __4 5__ 8 ) –> ( 1 2 __4 5__ 8 )<br>
( 1 2 4 __5 8__ ) –> ( 1 2 4 __5 8__ )<br>

```php
<?php
// Your code here!
function bubbleSort(&$arr) 
{ 
    $n = sizeof($arr); 
  
    // Traverse through all array elements 
    for($i = 0; $i < $n; $i++)  
    { 
        // Last i elements are already in place 
        for ($j = 0; $j < $n - $i - 1; $j++)  
        { 
            // traverse the array from 0 to n-i-1 
            // Swap if the element found is greater 
            // than the next element 
            if ($arr[$j] > $arr[$j+1]) 
            { 
                $t = $arr[$j]; 
                $arr[$j] = $arr[$j+1]; 
                $arr[$j+1] = $t; 
            } 
        } 
    } 
} 
// Driver code to test above 
$arr = array(64, 34, 25, 12, 22, 11, 90); 
  
$len = sizeof($arr); 
bubbleSort($arr); 
  
echo "Sorted array : \n"; 
  
for ($i = 0; $i < $len; $i++) 
    echo $arr[$i]." ";  
  
// This code is contributed by ChitraNayal. 
?>
```

```php
function bubbleSort(array $arr)
    {
        $n = sizeof($arr);
        for ($i = 1; $i < $n; $i++) {
            for ($j = $n - 1; $j >= $i; $j--) {
                if($arr[$j-1] > $arr[$j]) {
                    $tmp = $arr[$j - 1];
                    $arr[$j - 1] = $arr[$j];
                    $arr[$j] = $tmp;
                }
            }
        }

        return $arr;
    }

    // Example:
    $arr = array(255,1,22,3,45,5);
    $result = bubbleSort($arr);
    print_r($result);
//====================================================
//------- improved version----------------------------
//====================================================    
function bubbleSortImproved(array $arr)
{
    $n = sizeof($arr);    
    for ($i = 1; $i < $n; $i++) {
        $flag = false;
        for ($j = $n - 1; $j >= $i; $j--) {
            if($arr[$j-1] > $arr[$j]) {
                $tmp = $arr[$j - 1];
                $arr[$j - 1] = $arr[$j];
                $arr[$j] = $tmp;
                $flag = true;
            }
        }
        if (!$flag) {
            break;
        }
    }

    return $arr;
}

// Example:
$arr = array(255,1,22,3,45,5);
$result = bubbleSortImproved($arr);
print_r($result);
```
