# Vocabulary-Trainer
Task is to program a small and fast vocabulary trainer. Two small example files with vocabularies for professions and animals given in german and english language are given for tests. The vocabulary trainer shall be realised by a so called associative array. An associative array is an array which uses strings instead of natural numbers as indices, which are called keys. Since they are often used for electronic dictionaries associative arrays are called dictionaries, too.


Examples :
  Key -> Value
  hashtable["Hund"] -> "dog"
  hashtable["Katze"] -> "cat"
  hashtable["Maus"] -> "mouse"
  hashtable["Vogel"] -> "bird"
  
 To realise such associative arrays so called hashing or hash tables can be used. For these from the string called key a natural number is calculated as index into a normal array.
The function generating a number from a string t as key is called hashing or hash function h(t), since the indices/used array elements in the normal array are typically scattered and not ordered/sorted giving the name to it.
There are different possibilities to define such hash functions. A simple idea is the division rest method. A given number p - most often chosen are prime numbers - defines the length of an array. For a string t (in 7-bit-ASCII code, therefore characters from 0 to 27−1=127) with letters t= "b1b2b3…bn" can then be calculated without number overflows:

![image](https://user-images.githubusercontent.com/29509292/140308154-5ab9086c-ef67-4424-8e10-5c00527ed0b6.png)


Examples Hashing Values: 
Let p=661.


![image](https://user-images.githubusercontent.com/29509292/140308189-0d1118e7-e692-4f54-98f5-d92407d467a5.png)


Such a hash function allows to map arbitrary long strings - a huge infinite number of strings - onto a finite number inbetween 0 and p−. It might happen that different strings tk, tl (and also further ones) are mapped onto the same number/index h(tk)=h(tl)=i. This is called a collision.
Different solutions exist to deal with such collisions. A very easy one is to increment the calculated index i in a loop by 1 (therefore i+1, i+2, ...) until the first free array element is found and use instead this. If during incrementing value p is reached counting proceeds at the first index of the array. This method is called linear collision strategy.
As smaller prime number p, the length of the array, will be, as more collisions can be expected. In the end maximum p elements can be stored in the array. Are there no collisions search is extremely fast (only O(1) time consumption plus the calculation of the hash value/index). Hashing tables with a big number p are used very often and preferred for many problems. Are there a lot of collisions search can get linear on the whole array (for m≤p entires in the array O(m) time consumption).
