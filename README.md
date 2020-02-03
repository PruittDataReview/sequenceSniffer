# sequenceSniffer
authored by https://github.com/alrutten 

flags members of sequences of at least the specified length that appear at least twice in the specified data columns.

  * reformats specified columns to `long` format
  * calculates n-grams starting at the specified minimum sequence length
  * marks data points that are part of an n-gram that occurs at least twice
  * increases n-gram length until no more duplicate n-grams are found.
  
 ##### please note
 
 * the function does not yet check for overlapping sequences within a specific n-gram length, i.e. a sequence "A A B A A B A" will count and mark n-gram "A A B A" as duplicated
 * longer sequences will overwrite shorter sequences that they overlap with, i.e., in the above example,3-gram "A B A" will be overwritten by 4-gram "A A B A".

#### also please note

  * use your brain when interpreting the results.
  * finding sequences in data with very low cardinality is normal.
  * finding sequences in censored data is normal.
  * if you pick odd grouping levels, the randomisation test will give you similarly odd results.

#### static version

  * supply csv filename  
  * provide column range
  * set minimum sequence length
  * knit document
  
  -> displays your data with identified repeat-sequence member ship colour-coded
  
  -> randomly reorders data within a specified grouping level (e.g., original data columns & a `treatment` column in the orignal data) 1000 times and calculates the distribution of counts of datapoints that are part of a repeated sequence
  
#### dynamic version
  * run document
  * enter filename etc in UI
