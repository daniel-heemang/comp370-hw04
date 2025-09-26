1. How big is the dataset?
    
    ```bash
    $ ls -lh clean_dialog.csv 
    -rw-r--r-- 1 danielcho dcho 4.7M Sep 26 20:18 clean_dialog.csv
    $ wc -l clean_dialog.csv 
    36860 clean_dialog.csv
    ```

    The dataset is 4.7 MB or 36,859 lines long (excluding the header).

2. What's the structure of the data? i.e., what are the fields and what are the values in them?

    ```bash
    $ head clean_dialog.csv 
    "title","writer","pony","dialog"
    ```
    
    Each row of the dataset represents one line of dialogue.
    The dataset includes the following columns:
    - `title` is the title of the episode the line appears in.
    - `writer` is the writer of the episode the line appears in.
    - `pony` is the character saying the line.
    - `dialog` is the actual line itself.

3. How many episodes does it cover?

    ```bash
    $ csvtool col 1 clean_dialog.csv | tail -n +2 | sort | uniq | wc -l
    197
    ```

    The dataset covers 197 episodes.

4. During the exploration phase, find at least one aspect of the dataset that is unexpected—meaning that it seems like it could create issues for later analysis.

    The speaker column does not have consistent values. For example, it contains values:
    - `Main cast sans Twilight`
    - `Main cast sans Twilight Sparkle`