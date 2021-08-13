Document prepared by M. Gabriela Puscama

### Preparation of Corpus del Español to train LMOSS for co-occurrences

LMOSS (Lightweight Metric Of Semantic Similarity) is a software developed by Recchia & Jones (2009) to extract semantic similarity scores based on word co-occurrence in a corpus.

This script formats the corpus so it can be easily read by LMOSS.

Using the lemmatized version of the corpus, first I combined the files for each country into a single file using the Unix shell Git Bash. The Unix commands were:
#to change directory to the folder containing all the .txt files to be combined
cd ./folderpath
#to find all .txt files in the directory and merge them into a new combined file
cat *.txt > combined.txt  

Then using R I opened the file for each country and wrangled the data to create a new file with one column, each row containing one text (see Markdown "corpus-prep").

As part of the wrangling, I eliminated the rows that had symbols instead of words, and I replaced the letters with diacritics with doble letter (e.g., cana/caña, become cana and canna).

Finally, I used Unix once more to combine all the clean files for each country into a single file to train the model.