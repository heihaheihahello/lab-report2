## Fix bugs
> start with original MarkdownParse.java

---

* ### **bug-fix-1**

    - The test file that caused bug like [this](https://heihaheihahello.github.io/lab-report2/test-file1.md):

    ```
    # Title

    what ever text
    ```

    > In this test file, there is no links, no `[]` and `()`.
    - **Symptom**: The problematic output is: 
    ![Image](1w.jpg)
    > MarkdownParse.java got "StringIndexOutOfBoundsException" error.

    - Then we make the following change:
    ![Image](1_fix.jpg)

    - the fixed output: 

    ![Image](1fixed.jpg)
    > if there is no links, the output should be a single `[]` with nothing inside. Now the output is what we expected, we fixed the bug for this test file.

    - Analysis: Before we fixed, if there is no `[]` and '()', the index of all `[]()` will be `-1`. Then the `substring(0,-1)` will have error becuase from index `0` to `-1` is not existed. After We add a breaking point after we look for the first `[`, if there is no `[` existed in the file, the index will be -1 and then immediately break the loop. Then nothing is added in `toReturn` then the error on `substring` will be happened. So we will only output `[]`. 
    
      

