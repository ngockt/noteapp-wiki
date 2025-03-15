Brake down Domain of Science as the following

1. **Domain**: The broadest scope of knowledge or activity.  
2. **Field**: A recognized subdivision within a larger domain. Example: mathematics, physics, ... 
3. **Branch**: A narrower part of a field, focusing on a specific direction or methodology.  
4. **Subject**: A structured body of knowledge or curriculum, often taught or learned formally.  
5. **Topic**: A particular area of inquiry within a subject, narrower and more focused.  
6. **Concept**: A fundamental element or unit of understanding within a topic.

Return response as the following format
**Node CSV Format**:

```
id,name,tag,type  # Make sure to return the header
```

- `id`: The identifier for each entry, following the format: SHORT_FORM_OF_SUBJECT-SHORT_FORM_OF_NODE_TYPE-NUMBER, where SHORT_FORM_OF_NODE_TYPE can be one of (S, GT, T, C).
- `name`: The name of the subject, topic, or concept.
- `tag`: A short, hyphenated version of the name.
- `type`: The type of node, which can be one of:
  - `domain`
  - `field`
  - `subject`
  - `general-topic`
  - `topic`
  - `concept`

**Links CSV Format**:

```
src_node_id,dst_node_id,text,bidirectional  # Make sure to return the header
```

- `src_node_id`: ID of the source node.
- `dst_node_id`: ID of the destination node.
- `text`: The relationship type, which can be:
  - `contains`: Indicates a parent-child relationship.
  - `related`: Indicates a bidirectional relationship between two closely related nodes of the same type.
  - `prerequisite to`: Indicates that one node is a prerequisite for another, only applicable for nodes of the same type.
- `bidirectional`: `true` if the relationship is bidirectional (e.g., `related`), otherwise `false`.

Ensure that the nodes referenced in the links are valid.
Make sure it return valid csv content, be careful with text text value contain comma, it should be wrap by "..."