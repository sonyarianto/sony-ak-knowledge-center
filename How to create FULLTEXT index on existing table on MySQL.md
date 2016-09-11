```sql
CREATE FULLTEXT INDEX title_topic_short_content ON news(title, title_topic, short_content);
```

or

```sql
ALTER TABLE news  
ADD FULLTEXT(title, title_topic, short_content)
```
