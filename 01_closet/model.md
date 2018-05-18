## items

### model

- createdAt
- name
- id (primary key)
- tags
- url

```sql
CREATE TABLE IF NOT EXISTS items (
  id INT(4) AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  url VARCHAR(1024),
  createdAt DATETIME(0)
);
```

## tags

### model

- id
- name
- createdAt
- updatedAt

```sql
CREATE TABLE IF NOT EXISTS tags (
  id INT(4) AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  createdAt DATETIME(0),
  updatedAt DATETIME(0)
);
```

## items_tags

Relation table

```sql
CREATE TABLE IF NOT EXISTS items_tags (
  item_id INT(4),
  tag_id INT(4),
  PRIMARY KEY (item_id, tag_id),
  FOREIGN KEY (item_id) REFERENCES items (id) ON DELETE CASCADE ON UPDATE CASCADE,
  FOREIGN KEY (tag_id) REFERENCES tags (id) ON DELETE CASCADE ON UPDATE CASCADE
);
```
