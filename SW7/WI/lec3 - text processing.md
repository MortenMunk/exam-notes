**Text similarity**
- document similarity = two documents with similar contents
- string similarity

## Ranked retrieval model
**Simple model**
	- Ordering the top documents for a query, in order to get the most relevant 
		- most relevant are ranked highest
	- usually returns top k results, e.g. where k = ~10 to get top ten results
	- queries are in form of natural human language
	- ranked is based on how well document matches
	- A score between 0-1
	- e.g query with aalborg
		- If Aalborg does not occur in the document, score = 0
	
 **Jaccard coeffecient**
 - Term frequency is not considered
 - are terms are more informative than frequent
	 - e.g. adjectives such as good, beautiful

**Binary Term Document Incidence Matrix**
- Overview of documents, using matrix to describe content included and not included in specific documents
- Each document is a count vector with occurences of words

**Bag of words model**
- Vector representation does not consider occurences
- two sentences with different meaning, get same value (i think)

**Term Frequency**
- Relevance does not increase proportionally with term frequency$$tf(t,d)=t/d$$          where t is number of times term appears in documentd
					  and d is total number of terms in document

**Log Frequency weighting**
- another way to calculate term frequency
- ![[Pasted image 20240923131636.png]]

**Document Frequency**
- frequent terms = less informative
- lav vægt for ord der ofte forekommer
- ![[Pasted image 20240923133545.png]]

