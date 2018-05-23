# Pushshift Google BigQuery Data Streams

## Reddit

### Dataset location

pushshift.rt_reddit

### Tables

comments

### comments Table Schema
```
  Last modified                  Schema                  Total Rows   Total Bytes   Expiration      Time Partitioning       Labels  
 ----------------- ------------------------------------- ------------ ------------- ------------ -------------------------- -------- 
  23 May 01:14:24   |- author: string (required)          0            0                          DAY (field: created_utc)           
                    |- author_flair_text: string                                                                                     
                    |- author_flair_css_class: string                                                                                
                    |- body: string (required)                                                                                       
                    |- created_utc: timestamp                                                                                        
                    |- subreddit: string (required)                                                                                  
                    |- subreddit_id: integer (required)                                                                              
                    |- parent_id: string                                                                                             
                    |- link_id: string (required)                                                                                    
                    |- id: integer (required)                                                                                        
                    |- send_replies: boolean                                                                                         
                    |- stickied: boolean                                                                                             
                    |- subreddit_type: string                                                                                        
                    |- score: integer                                                                                                
                    |- gilded: integer                                                                                               
                    |- can_gild: boolean                                                                                             
                    |- controversiality: integer                                                                                     
                    |- is_submitter: boolean                                                                                         
                    |- no_follow: boolean                                                                                            
                    |- edited: timestamp                                                                                             
                    |- permalink: string                                                                                             
                    |- retrieved_on: timestamp                                                                                       
```                                                                                 

### Standard SQL Query Examples

How many comments have been made in the last minute?

    SELECT count(*) FROM `pushshift.rt_reddit.comments` WHERE created_utc > TIMESTAMP_SUB(CURRENT_TIMESTAMP, INTERVAL 1 MINUTE)
