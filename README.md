# compass_metadata_writer_tests
Contains test case inputs and outputs for compass_metadata_writer.

Following are the test cases for CMW


1.  Input: Episode 1: Contains RDF data for episode 1 of the TV show.
	Expected output: Sperated episode and series subgraph
    
2.  input: Episode 1: Contains same RDF data for episode 1 of the TV show.
	Expected output: No change in GMS
    
3.  Input: Episode 2: Contains RDF data for episode 2 of the TV show.
	Exp: Series data subtracted and onlly episode data should be written, and sholud conatain a triple to point to this series graph.
    
4.  Input: Giving edit of episode 1 : Contains an edit to the RDF data for episode 1.
	Exp: old episode data should be written into history graph and deleted from amagi. New data should be written into amagi.
    
5.  Input: Episode 3 Contains RDF data for episode 3 of the TV show, but with edits to the series data.
	Exp: old Series data to be written to history, deleted from amagi. new graph to be written into amagi.
    
6.  input: Giving edit of episode 3 : Contains an edit to the RDF data for episode 3, which includes both edits to the episode data and the series data.
	  Exp: Old episode data and old series data to be written into history and delted from amagi. New triples to be written to amagi.
	  
7.  Input: Feature 1: Contains RDF data for a feature of the TV show.
    Exp: Feature1 triples.
    
8.  input: Feature 2: Contains RDF data for another feature of the TV show.
    Exp: Feature2  triples.
    
9.  input: Giving edit of feature 1: Contains an edit to the RDF data for feature 1.	
	Exp: old feature 1 data should be written into history graph and deleted from amagi. New triples should be written into amagi.

TODO:

1. Empty TTL file
2. Very Large ttl file
3. Asset without "a ns1:Episode or ns1:Feature"
4. Episode Asset without any Series Triples
5. Asset without publisher ID
6. Invalid ttl file 
7. Episode asset with already containing ns1:isEpisodeOfSeries triple (single triple)
7. Episode asset with two separate series triples (ns1:isEpisodeOfSeries )
8. Feature asset with contains ns1:isEpisodeOfSeries
9. 