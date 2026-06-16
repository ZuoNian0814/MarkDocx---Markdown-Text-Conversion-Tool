# Markdown 编写守则 🧾 (测试版)
# Markdown Writing Guide (Beta)

---

## 📖 概述 / Overview

本文档规范了 Markdown 的编写方式，确保所有元素能正确适配对应的转换程序。
This document standardizes the Markdown writing style to ensure all elements are correctly adapted to the corresponding conversion program.

---

## ✅ 支持的块级元素 / Supported Block Elements

### 1. 标题 (Heading) / 1. Headings

支持六级标题（H1 – H6），标题字体大小随级别递减。
Supports six levels of headings (H1–H6), with font size decreasing per level.

**示例 / Example**:
```markdown
# 一级标题 / Heading 1
## 二级标题 / Heading 2
### 三级标题 / Heading 3
#### 四级标题 / Heading 4
##### 五级标题 / Heading 5
###### 六级标题 / Heading 6
```

---

### 2. 引用 (Blockquote) / 2. Blockquotes

- 使用 `>` 符号表示引用。
- 支持单层引用和嵌套引用（使用 `> >` 实现，呈现时以不同程度的缩进体现层级）。
- Use `>` for blockquotes.
- Supports single and nested blockquotes (`>>` for nesting, shown with different indentation levels).

**示例 / Example**:
```markdown
> 块引用示例 / Blockquote example
> 引用示例2 / Quote example 2

> 嵌套引用示例 / Nested blockquote example
> > 嵌套引用 / Inner nested quote
```

---

### 3. 分隔符 / 3. Thematic Break (Page Break)

- 使用三个或以上的 `-`（例如 `---`）或 `***`、`___` 表示。  
Use three or more `-` (e.g. `---`) or `***`, `___`.
- 转换时分隔符会自动生成为**分页符**，即前后内容不在同一页面。  
Converted to a **page break** – content before and after will be on different pages.

**示例 / Example**:
```markdown
第一页内容 / Page 1 content

---

第二页内容 / Page 2 content
```

---

### 4. 图片 (Image) / 4. Images

- 使用 `![alt](path)` 语法。  
Use `![alt](path)` syntax.
- 支持相对路径或绝对路径。  
Supports relative or absolute paths.

- 图片下方自动生成图题，格式为 `图1 图片描述`，12号居中。编号自增（图1、图2…），与引用编号独立。  
An automatic caption `Fig. 1 Image description` is generated below the image, centered, font size 12. Numbering is independent from blockquotes.

**示例 / Example**:
```markdown
![图像描述 / Image description](./images/sample.png)
```

---

### 5. 代码 (Code) / 5. Code

- **行内代码 / Inline code**: 使用反引号 `` ` `` 包围。转换时按普通文本处理，不设置等宽字体。
  Wrapped in backticks. Treated as normal text without monospace font.
- **代码块 / Code block**: 使用三个反引号 `` ``` `` 包裹并可选语言标识。代码块内容**会被保留**，以等宽字体显示，并保留换行和缩进。
  Wrapped in triple backticks with optional language identifier. Content **is preserved** with monospace font, line breaks, and indentation.

**示例 / Example**:
```markdown
这是 `行内代码 / inline code` 示例。

\```python
for i in range(5):
    print(f"循环变量 / loop variable {i}")
\```
```

---

### 6. 表格 (Table) / 6. Tables

- 使用标准 GFM 表格语法（行首 `|` 分隔列，第二行指定对齐 `:---`、`:---:`、`---:`）。  
Use standard GFM table syntax.
- **所有表格默认居中对齐**，无论对齐设置 ( `:---` 左对齐, `:---:` 居中, `---:` 右对齐 ) 均视为居中。  
**All tables are centered by default** regardless of alignment markers (`:---` left, `:---:` center, `---:` right).

- 表头行必须存在，分隔行必须存在。  
Header row and separator row are mandatory.
- 单元格内支持普通文本、加粗、斜体、行内代码、图片等内联元素。  
Cells support plain text, bold, italic, inline code, images, etc.

**示例 / Example**:
```markdown
| 标题1 / Header1 | 标题2 / Header2 | 标题3 / Header3 |
|:----------------|:---------------:|----------------:|
| 表格行1 / Row1  | 文本 / Text    | 文本 / Text     |
| ![图片](./img.png) | 文本 / Text    | 文本 / Text     |
```

---

### 7. 列表 (List) / 7. Lists

- **有序列表 / Ordered list**: 使用数字加点 (`1.`, `2.`)。转换时保留数字编号样式。  
Ordered list uses `1.`, `2.` etc. Numbering style is preserved.
- **无序列表 / Unordered list**: 使用 `-`, `*` 或 `+`。转换时以项目符号显示。  
Unordered list uses `-`, `*`, `+`. Shown with bullet points.
- 支持列表嵌套（通过缩进实现），嵌套层级以不同缩进或符号表示。  
Supports nesting by indentation.

**示例 / Example**:

无论是无序还是有序列表都会被编入有序编号。  
Both unordered and ordered lists will be included in ordered numbering.

```markdown
1. 第一项 / Item 1
2. 第二项 / Item 2
3. 第三项 / Item 3
```

---

## ✨ 支持的内联样式 / Supported Inline Styles

| 样式 / Style | 语法 / Syntax | 说明 / Description |
|:---:|:---:|:---|
| **加粗 / Bold** | `**文字**` | 粗体显示 / Bold text |
| *斜体 / Italic* | `_文字_` 或 `*文字*` | 斜体显示 / Italic text |
| **加粗嵌套斜体 / Bold with Italic** | `**加粗 _斜体_**` | 粗体文字中嵌套斜体 / Bold text containing italic |
| `行内代码 / Inline code` | `` `code` `` | 普通文本，不设等宽 / Plain text, no monospace |

---

## ⚠️ 注意事项 / Important Notes

1. 所有 Markdown 文件必须使用 **UTF-8** 编码。  
   All Markdown files must use **UTF-8** encoding.

2. 引用计数和图片计数各自独立，均从1开始递增。  
   Blockquote numbering and image numbering are independent, both starting from 1.

3. 分隔符（`---`）前后需有空白行，避免被误识别为标题。  
   Insert blank lines before and after `---` to avoid being misinterpreted as a heading.

4. 表格必须连续编写（表头、分隔行、每行之间不能有空行）。  
   Tables must be written continuously (no blank lines between header, separator, and rows).

5. 代码块中的语言标识仅为语法高亮参考，转换时不影响内容显示。  
   The language identifier in code blocks is for syntax highlighting reference only; does not affect content display.

6. 表格内嵌套图片会生成图题，但图片编号可能超出文档预期，建议仅在特殊需求下使用。  
   Nested images in table cells generate captions, but caption numbering may become unexpected; use only when necessary.

--
