# Sample data
```mermaid
graph LR
    subgraph pages
        page_1
    end

    subgraph page_versions
        page_1_v1
    end
    subgraph blocks
        block_1_v1
    end


    subgraph block_contents
        block_1_v1_en
        block_1_v1_vi
    end

    page_1 <--> page_1_v1
    page_1_v1 <--> block_1_v1
    block_1_v1 <--> block_1_v1_en
    block_1_v1 <--> block_1_v1_vi
```
# New Block
```mermaid
graph LR
    classDef new_block fill:#FFDDC1,stroke:#333,stroke-width:2px;
    subgraph pages
        page_1
    end

    subgraph page_versions
        page_1_v1
    end
    subgraph blocks
        block_1_v1
        block_2_v1
    end


    subgraph block_contents
        block_1_v1_en
        block_1_v1_vi
        block_2_v1_en
        block_2_v1_vi
    end

    page_1 <--> page_1_v1

    page_1_v1 <--> block_1_v1
    page_1_v1 <--> block_2_v1

    block_1_v1 <--> block_1_v1_en
    block_1_v1 <--> block_1_v1_vi

    block_2_v1 <--> block_2_v1_en
    block_2_v1 <--> block_2_v1_vi

    class block_2_v1,block_2_v1_en,block_2_v1_vi new_block;
```
# New created Version
```mermaid
graph TD
    classDef new_block fill:#FFDDC1,stroke:#333,stroke-width:2px;
    subgraph pages
        page_1
    end

    subgraph page_versions
        page_1_v1
        page_1_v2
    end
    subgraph blocks
        subgraph v1
            block_1_v1
            block_2_v1
        end
        subgraph v2
            block_3_v2
            block_4_v2
        end
    end


    subgraph block_contents
        block_1_v1_en
        block_1_v1_vi
        block_2_v1_en
        block_2_v1_vi
    end

    page_1 <--> page_1_v1

    page_1_v1 <--> block_1_v1
    page_1_v1 <--> block_2_v1

    page_1_v2 <--> block_3_v2
    page_1_v2 <--> block_4_v2

    block_1_v1 <--> block_1_v1_en
    block_1_v1 <--> block_1_v1_vi

    block_2_v1 <--> block_2_v1_en
    block_2_v1 <--> block_2_v1_vi


    block_3_v2 <--> block_1_v1
    block_4_v2 <--> block_2_v1


    class page_1_v2 new_block;
```


## New version: clone content of latest version by s
## Make a new language
 in a version will clone all the block content of the source language, A page-version languages must have same number of blocks and orders
## New block 
Adding new block to a language, it will appear in other language as well