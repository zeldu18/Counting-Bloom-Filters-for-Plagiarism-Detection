# Counting-Bloom-Filters-for-Plagiarism-Detection

A more advanced solution involves employing multiple hash functions ( ) to replace
ℎ1, ℎ2, ℎ3,...
a 1 in each of the different slots that the set of hash functions being used return for a given
element . This approach minimizes the likelihood of multiple elements pointing to the exact
𝑒
same set of slots, reducing the chance of false positives.
Despite this improvement, the possibility of false positives, where an element is mistakenly
identified as in the set when it is not, still exists. The frequency of false positives depends on
factors such as the number of items and the number of hash functions employed.
Overall, although we do not eliminate the possibility of false positives, Bloom Filters can make
such a possibility more unlikely (compared to the solutions described above).
However, we encounter another problem when removing items. Bloom Filters using binary
values (0 or 1) may lead to a problem when an item is deleted, it affects the slots of other
elements. A solution to this problem is the Counting Bloom Filters. Instead of a single bit of
information (0 or 1), each cell of the table has a (n-bit) counter. This counter increments every
time a value is inserted, and decrements every time an item is removed.
For example, when you sell a coat , all the bloom filter counters of the corresponding slots of
𝑒
this element go down by one. Later, when we search for , we would expect that at least one of
𝑒
the corresponding slots would have gone down to 0 and return “not found”. In a less likely case,
if enough other elements were “inserted” in the same slots corresponding to , the search would
𝑒
return a false positive.
