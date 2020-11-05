# v4-hathi-indexer
The code here will contact hathitrust and download the latest updates to their materials, determine which are publically accessible, and which are not publically accessible, and will add those updates to the ingest queues for the staging or production indexes.

The top level script to be executed is updateifnewer.   It accepts the command line arguments of
-  -v  verbose   
-  -t  test (downloads files but doesn't send anything to solr input queues)
-  -a  force a check of whether the AWS environment variables are defined
-  -i  <arg>   specify which indexes are to be updated  staging  or production or staging:production
  
If there is a locally maintained cache of all records (in the full_dump directory under the data directory) the update process will merge the updates into that cache ensuring it is up to date.  At present the scripts for initially populating the cache of records is only half-ported, and resides in the bak directory.
  
