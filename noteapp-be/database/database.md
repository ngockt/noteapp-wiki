# Prompt
I have an app that has following the features:
- view/add/edit/delete note
- the app has components structure like the below:
  - Subjects (eg: Calculus) contains topics (eg: limit, continually)
  - each card must
- there are different type of cards, with different functionality
  - video card, need to store video url
  - note card, need to store image path
  - audio card, need to store audio path
- the app has list of tags, which can be put in cards, and has the feature to group cards
- the cards can be link/map with each other
- feature to monitor how many time the card has been view, pick, ...
- 

Design me a SQL database using markdown mermaid for the above features.
put the response in ```` ... ````

# Architecture

```mermaid
erDiagram

    NOTE {
        int id PK
        varchar title
        text content
        datetime created_at
        datetime updated_at
    }

    CARD {
        int id PK
        varchar type
        int view_count
        int pick_count
        datetime created_at
        datetime updated_at
    }

    VIDEO_CARD {
        int id PK
        int card_id FK
        varchar video_url
    }

    NOTE_CARD {
        int id PK
        int card_id FK
        varchar image_path
    }

    AUDIO_CARD {
        int id PK
        int card_id FK
        varchar audio_path
    }

    TAG {
        int id PK
        varchar name
    }

    CARD_TAG {
        int id PK
        int card_id FK
        int tag_id FK
    }

    CARD_LINK {
        int id PK
        int source_card_id FK
        int target_card_id FK
        varchar link_type
    }

    GROUP {
        int id PK
        varchar name
        datetime created_at
        datetime updated_at
    }

    CARD_GROUP {
        int id PK
        int card_id FK
        int group_id FK
    }

    NOTE ||--o| CARD : "contains"
    CARD ||--|{ VIDEO_CARD : "is a"
    CARD ||--|{ NOTE_CARD : "is a"
    CARD ||--|{ AUDIO_CARD : "is a"
    CARD ||--|{ CARD_TAG : "has"
    TAG ||--|{ CARD_TAG : "applies to"
    CARD ||--|{ CARD_LINK : "links to"
    CARD ||--o| CARD_LINK : "is linked to"
    GROUP ||--|{ CARD_GROUP : "groups"
    CARD ||--|{ CARD_GROUP : "is part of"
```
