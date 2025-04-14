## Tools Directory Structure

- [**Strategy Development Main**](../README.md)
  - [Tools Main](./tools.md)
    - [Github](./github.md)
    - [Markdown Cheatsheet](./markdown_cheatsheet.md)
    - [VS Code](./vs_code.md)
    - [Communication](./communication.md)
    - [Platform Integrations](./platform_integrations.md)
    - [Additional Resources](./additional_resources.md)

---

# Markdown Cheatsheet

This **Markdown Cheatsheet** covers both **basic syntax** (common to all Markdown parsers) and **GitHub Flavored Markdown** (GFM) extensions. Use this document as a quick reference for writing `.md` files in GitHub repositories.

---

## 1. Headings

Use `#` symbols for headings. The number of `#` represents the heading level.

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

**Result:**

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

---

## 2. Paragraphs & Line Breaks

- Separate paragraphs with a blank line.  
- For a line break within a paragraph, end a line with **two or more spaces**, then press Enter.

```markdown
This is a paragraph.

This is a new paragraph.

Line with two spaces at the end for  
a manual line break.
```

---

## 3. Emphasis

```markdown
*Italic text* or _Italic text_  
**Bold text** or __Bold text__  
~~Strikethrough~~
```

**Result:**

- *Italic text* or _Italic text_  
- **Bold text** or __Bold text__  
- ~~Strikethrough~~

---

## 4. Lists

### 4.1 Unordered Lists

Use `-`, `*`, or `+` followed by a space.

```markdown
- Item 1
- Item 2
  - Sub-item (indent by 2 spaces)
- Item 3
```

**Result:**

- Item 1
- Item 2
  - Sub-item (indent by 2 spaces)
- Item 3

### 4.2 Ordered Lists

Use numbers followed by a period.

```markdown
1. First item
2. Second item
3. Third item
```

**Result:**

1. First item
2. Second item
3. Third item

### 4.3 Task Lists (GitHub Flavored)

GitHub supports **task lists** where checkboxes can be checked in the UI:

```markdown
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task
```

**Result (in GitHub):**

- [x] Completed task  
- [ ] Incomplete task  
- [ ] Another task  

---

## 5. Links & URLs

```markdown
[Hyperlink text](https://example.com)

Bare URL (GitHub often auto-links): https://example.com

Reference-style link:
[Click me][id1]

[id1]: https://example.com "Optional Title"
```

**Result:**

- [Hyperlink text](https://example.com)  
- https://example.com  
- [Click me][id1]

[id1]: https://example.com "Optional Title"

---

## 6. Images

```markdown
![Alt text](https://example.com/image.jpg "Optional Title")

Reference-style:
![Alt text][img-ref]

[img-ref]: https://example.com/image.jpg
```

**Result:**

- ![Alt text](https://via.placeholder.com/100 "Optional Title")

---

## 7. Code Blocks & Inline Code

### 7.1 Inline Code

Wrap code snippets with backticks:

```markdown
Use `inline code` for small code references.
```

**Result:**  
Use `inline code` for small code references.

### 7.2 Fenced Code Blocks

Surround code with triple backticks. Specify a language for syntax highlighting:

<pre><code>```python
print("Hello, world!")
```
</code></pre>

**Result (with syntax highlighting):**

```python
print("Hello, world!")
```

---

## 8. Blockquotes

Use `>` at the beginning of a line:

```markdown
> This is a blockquote.
> 
> It can span multiple lines or paragraphs.
```

**Result:**

> This is a blockquote.  
>  
> It can span multiple lines or paragraphs.

---

## 9. Horizontal Rules

Create a horizontal rule (line) with three or more `*`, `-`, or `_` on a line by themselves:

```markdown
---
```

**Result:**  
---

---

## 10. Tables

GitHub Flavored Markdown supports table syntax:

```markdown
| Column A | Column B | Column C |
|----------|----------|----------|
| Item 1A  | Item 1B  | Item 1C  |
| Item 2A  | Item 2B  | Item 2C  |
```

**Result:**

| Column A | Column B | Column C |
|----------|----------|----------|
| Item 1A  | Item 1B  | Item 1C  |
| Item 2A  | Item 2B  | Item 2C  |

You can align columns by using colons:

```markdown
| Left Aligned | Center Aligned | Right Aligned |
|:------------ |:--------------:| -------------:|
| Text         | Text           | Text          |
| More Text    | More Text      | More Text     |
```

---

## 11. GitHub Flavored Markdown (GFM) Extensions

### 11.1 Task Lists

See [Lists → Task Lists](#43-task-lists-github-flavored) above.

### 11.2 @Mentions

When you type `@username`, GitHub notifies that user:

```markdown
Thanks for the update, @johnsmith!
```

**Result (on GitHub):**  
Thanks for the update, @johnsmith!

### 11.3 References to Issues and Pull Requests

Type `#` followed by the issue or PR number to create a link:

```markdown
Fixes #123
See PR #456
```

**Result (on GitHub):**  
- Fixes #123  
- See PR #456  

(The text `#123` becomes a link to the issue or PR.)

### 11.4 Emoji

You can add emojis using colon syntax:

```markdown
:smile: :rocket: :heart:
```

**Result (on GitHub):**  
:smile: :rocket: :heart:

Also see these emoji cheatsheets:

- [GitHub Emoji Cheat Sheet (Rxaviers)](https://gist.github.com/rxaviers/7360908)
- [Emoji Cheat Sheet by WebpageFX](https://www.webpagefx.com/tools/emoji-cheat-sheet/)

#### 11.4.1 Emoji Cut & Paste Icons

Cut and paste these icons into your markdown file.

 - ✅
 - 👉
 - 🚩
 - 🏆
 - 🖥️
 - ⚡
 - 🛠️
 - 🚨
 - 📌
 - ⚙️
 - 

### 11.5 Syntax Highlighting for Code Blocks

GitHub automatically supports many languages (e.g., `python`, `javascript`, `csharp`). Just specify the language right after the triple backticks:

```markdown
```csharp
// C# example
Console.WriteLine("Hello, GitHub!");
```
```

---

## 12. Miscellaneous

### 12.1 Escaping Special Characters

To display literal characters like `*` or `_`, use a backslash:

```markdown
\*Not italic\*
```

**Result:**  
\*Not italic\*

### 12.2 HTML in Markdown

GitHub Flavored Markdown supports inline HTML for more advanced formatting:

```markdown
<b>Bold</b> HTML tags can be used, but it's often best to stick to pure Markdown.
```

---

## 13. Additional Tips

- **Line Length**: For readability, keep lines at a reasonable length (e.g., 80–120 characters).  
- **Consistency**: Use consistent heading levels, indentation, and bullet styles.  
- **Preview**: Use GitHub’s preview tab (or a Markdown preview extension in VS Code) to ensure correct rendering before committing.

---

## 14. Further Resources

- [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)
- [GitHub Docs: Working with Advanced Formatting](https://docs.github.com/en/github/writing-on-github)

---

**Enjoy writing in Markdown!** This syntax helps keep your `.md` files organized, legible, and version-controlled—all essential for effective collaboration on GitHub.


