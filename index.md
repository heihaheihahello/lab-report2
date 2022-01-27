## Fix bugs
> start with original MarkdownParse.java

---

* ### **bug-fix-1**

    - The test file that caused bug like [this](https://heihaheihahello.github.io/lab-report2/test-file1.md):

    ```
    # Title

    (https://something.com)

    ```
    
    > In this test file, there is no links.
    - **Symptom**: The problematic output is: 
    ![Image](1w.jpg)
    > we can see MarkdownParse.java got in infinite loop.

    - Then we make the following change:
    ![Image](1fix.jpg)

    - the fixed output: 
    ![Image](1fixed.jpg)
    > if there is no links, the output should be a single `[]` with nothing inside. Now the output is what we expected, we fixed this bug.

    - Analysis: We add a breaking point after we look for the first `[`, if there is no `[` existed in the file, the index will be -1 and then immediately break the loop. Then nothing is added in `toReturn` as there is no links in the file. So we will only output `[]`. 
    
      

