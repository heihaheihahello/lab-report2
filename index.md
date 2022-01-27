## Lab report 2
> start with original MarkdownParse.java
---
* ### **bug-fix-1**

    - The test file that caused bug is [this](https://heihaheihahello.github.io/lab-report2/test-file1.md):
    ```
    # Title

    [a link!](https://something.com)
    Hi
    ```
    - **Symptom**: The problematic output is: 
    ![Image](1w.jpg)
    > we can see MarkdownParse.java got in infinite loop.

    - Then we make the following change:
    
