# 4D-Tech-Tips
Authored Numerous Technical Tips Sharing My Expertise and Experience with the 4D Community. 

Example: 
## Reduce Collection

### Description
The Utility Method ***reduceCollection()*** accepts a collection as parameter and returns its reduced collection
| Parameter | Type     |       Description        |
| --------- |----------|--------------------------|
| $coll     |Collection| Collection to be reduced |


### Example
```4d
var $coll1; $coll2; $coll3; $newColl1; $newColl2; $newColl3: Collection
$coll1:=New collection
$coll1.push(New collection(0;1))
$coll1.push(New collection(2;3))
$coll1.push(New collection(4;5))

$coll2:=New collection
$coll2.push(New collection("text1"; "text2"))
$coll2.push(New collection("text3"; "text4"))

$coll3:=New collection
$coll3.push(New collection("name1"; New collection("name2"; "text")))
$coll3.push(New collection("name3"; New collection("name4"; "text")))

$newColl1:=reduceCollection($coll1)// [0,1,2,3,4,5]
$newColl2:=reduceCollection($coll2)// ["text1", "text2", "text3", "text4"] 
$newColl3:=reduceCollection($coll3) // ["name1",["name2","text"],"name3",["name4","text"]]
```
>Tech Tip: <https://kb.4d.com/assetid=79066>

Notice with $newColl1 and $newColl2 the Collections being passed to the utility method contain several collection elements and those collection elements are returned in a single Collection. The Collection $coll3 is reduced and the result is stored in $newColl3

[![logo 4D blog with link](https://blog.4d.com/wp-content/uploads/2016/09/logoOrignal.png)](https://blog.4d.com)
><https://blog.4d.com/the-use-of-formulas-in-collections-callback-commands/>
