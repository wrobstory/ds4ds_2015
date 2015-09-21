# ds4ds 2015
### [Lightning Talk: Column Compression](ColumnarCompression_Story_DS4DS.pdf)

These slides were thrown together quickly to stress one point: with dataframe-like things, we should think about developer APIs in terms of abstracting the storage model from the operations on tuples or vectors. I want to be able to plug-in new array/column compression types and have the operations on those columns "just work". A lot of thought went in to this for C-Store almost a decade ago. They figured out a set of API methods (`isOneValue`, `getNext`, `isValueSorted`, etc, see slide 13) that would abstract away the implementation details of the column compression. If we're going to move towards more out-of-core tools such as Dato's SFrame and Wise's WiseDataSet, this is going to have to be a consideration.

Some of the examples were largely taken from the [Redshift docs](http://docs.aws.amazon.com/redshift/latest/dg/c_Compression_encodings.html)

The other examples were taken from my notes on the following papers:

Abadi [Query Execution in Column-Oriented Database Systems](http://cs-www.cs.yale.edu/homes/dna/papers/abadiphd.pdf)

Abadi, et al., [The Design and Implementation of Modern Column-Oriented Database Systems](http://db.csail.mit.edu/pubs/abadi-column-stores.pdf)
