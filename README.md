## Term Frequency with sklearn fetch_20newsgroups dataset
Term Frequency with sklearn fetch_20newsgroups dataset
### Data Preprocessing
##### Delete email, number, non-word that doesn't need, and create data frame
```
                                               News  Target
0  From Mamatha Devineni Ratnam Subject Pens fans...      10
1  From Matthew B Lawson Subject Which high perfo...       3
2  From hilmi Hilmi Eren Subject Re ARMENIA SAYS ...      17
3  From Guy Dawson Subject Re IDE vs SCSI DMA and...       3
4  From Alexander Samuel McDiarmid Subject driver...       4
```
##### Delete Stopwords with stopwords.words('english')
```
0        Mamatha Devineni Ratnam Subject Pens fans reac...
1        Matthew B Lawson Subject Which high performanc...
2        hilmi Hilmi Eren Subject Re ARMENIA SAYS IT CO...
3        Guy Dawson Subject Re IDE vs SCSI DMA detach O...
4        Alexander Samuel McDiarmid Subject driver Orga...
                               ...                        
18841    jim Jim Zisfein Subject Re Migraines scans Dis...
18842    richard b dell Subject Re A question 1 VAC out...
18843    Will Estes Subject Mounting CPU Cooler vertica...
18844    steve hcrlgw Steven Collins Subject Re Sphere ...
18845    Chris Silvester Subject Production Hold 9 Fire...
Name: News, Length: 18846, dtype: object
```
### Create tf vectorizer
```
<18846x74568 sparse matrix of type '<class 'numpy.int64'>'
	with 2104915 stored elements in Compressed Sparse Row format>
```
### Show the word by tf scoring
```
tf_scores = tf_vector.toarray().sum(axis=0)
tf_idx = np.argsort(-tf_scores)
tf_scores = tf_scores[tf_idx]
tf_vocab = np.array(tf_vectorizer.get_feature_names())[tf_idx]
print(list(zip(tf_vocab, tf_scores))[:100])
```
