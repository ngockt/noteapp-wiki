List all the topics and concepts of subject Linear Algebra in the following format:
- General topics contain detailed topics.
- Each detailed topic contains at least 2 concepts. If a topic can not be broken down to more than 2 concepts, it should stay as a concept.
- Concepts are the smallest elements that cannot be broken down further and are self-explanatory.
- Nodes of the same type can be related or be prerequisites to each other.
- Choose a short and concise names for topics and concepts

**Node CSV Format**:

```
id,name,tag,type  # Make sure to return the header
```

- `id`: The identifier for each entry, following the format: SHORT_FORM_OF_SUBJECT-SHORT_FORM_OF_NODE_TYPE-NUMBER, where SHORT_FORM_OF_NODE_TYPE can be one of (S, GT, T, C).
- `label`: The name of the subject, topic, or concept.
- `tag`: A short, hyphenated version of the name.
- `type`: The type of node, which can be one of:
  - `general-topic`: A broad category within the subject.
  - `topic`: A detailed topic within a general topic.
  - `concept`: A specific, granular idea within a topic.
**Links CSV Format**:
```
src_node_id,dst_node_id,text,bidirectional  # Make sure to return the header
```

- `src_node_id`: ID of the source node.
- `dst_node_id`: ID of the destination node.
- `label`: The relationship type, which can be:
  - `next`: Indicates that this general topics should be be studyied before go to the next general topics
  - `contains`: Indicates a parent-child relationship. 
  - `related`: Indicates a bidirectional relationship between two closely related nodes of the same type.
  - `prerequisite to`: Indicates that one node is a prerequisite for another, only applicable for nodes of the same type.
- `bidirectional`: `true` if the relationship is bidirectional (e.g., `related`), otherwise `false`.

Ensure that the nodes referenced in the links are valid.
Make sure it return valid csv content, be careful with text text value contain comma, it should be wrap by "..."