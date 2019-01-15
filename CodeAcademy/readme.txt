I think I found 2 errors:

1) In "Scoring Similarity with All Three Indicators" there is a line that says:

Calculate the difference between their two-word ngram using frequency_table on both TextSample's ngram_frequency attributes. Save that into a variable called ngram_similarity.

I think "frequency_table" should say "frequency_comparison"

2) In "Comparing Average Sentence Length" the formula for percent difference can have a value > 1.  For example, if value1 = 2 and value2 = 50, the formula says that the percent difference is 48/26 = 1.846.
This is important because in "Scoring Similarity with All Three Indicators" you compute the inverse of sentence_length_difference with abs(1 - sentence_length_difference).  This is not correct if sentence_length_difference
is greater than 1, which it is for Myrtle Beech - for whom I calculated sentence_length_difference = 1.04.  I, nevertheless, left the abs(1 - sentence_length_difference) in the find_text_similarity function as you suggested.
When I changed the formula to abs(2 - sentence_length_difference), which works for this project as none of the sentence_length_difference values is greater than 2, then the murderer is still Lily Trebuchet.
