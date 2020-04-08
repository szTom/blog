
# 1 Atom markdown
## 1.1  markdown-preview
https://atom.io/packages/markdown-preview
Markdown预览
- Edit \ preferences \ Packages \ markdown-preview
  - 默认已打开的
- Packages \ Markdown Preview \ Toggle Github Style
  - 切换为Github风格
- Edit \ Stylesheet...
  - 编辑styles.less样式表

> .markdown-preview.markdown-preview {
>   background-color: #fff;
> }
- markdown-preview 页面 右键单击预览的任何空白区域
  - 单击“Save As HTML” ...获得html文件。

## 1.2  增强预览(markdown-preview-plus)

https://atom.io/packages/markdown-preview-plus <br>
https://github.com/atom-community/markdown-preview-plus/blob/master/docs/installation.md
- Edit \ preferences \ Install \ 搜索: markdown preview plus
  - Install 安装插件
- Edit \ preferences \ Packages \ markdown-preview
  - Atom已自动关闭了markdown-preview，若没有，可以在这里手动关闭

Atom自带的Markdown预览插件markdown-preview功能比较简单，markdown-preview-plus对其做了功能扩展和增强。
1. 支持预览实时渲染。(Ctrl + Shift + M)
2. 支持Latex公式。(Ctrl + Shift + X)
3. (可选)在引用支持下使用pandoc(通用文档转换器)

https://pandoc.org/
> $ sudo pacman -S pandoc

(← = conversion from; → = conversion to; ↔︎ = conversion from and to)
- Word processor formats
  - ↔︎ Microsoft Word docx
  - ↔︎ OpenOffice/LibreOffice ODT
  - → OpenDocument XML
  - → Microsoft PowerPoint
- HTML formats
  - ↔︎ (X)HTML 4
  - ↔︎ HTML5
- Ebooks
  - ↔︎ EPUB version 2 or 3
  - ↔︎ FictionBook2
- Data formats
  - ← CSV tables
- PDF
  - → via pdflatex, xelatex, lualatex, pdfroff, wkhtml2pdf, prince, or weasyprint.
- Lightweight markup formats
  - ↔︎ Markdown (including CommonMark and GitHub-flavored Markdown)
  - ... 还有更多，请参阅官网

# 2 更多软件包
1. 同步滚动(markdown-scroll-sync)
   - https://atom.io/packages/markdown-scroll-sync
2. 代码增强(language-markdown)
   - https://atom.io/packages/language-markdown
   - 添加了对Markdown的语法支持(including Github flavored, AtomDoc, Markdown Extra, CriticMark, YAML/TOML front-matter, and R Markdown)，以及列表中的智能上下文感知行为和内联重点的键盘快捷键。
3. 图片粘贴(markdown-image-paste)
   - https://atom.io/packages/markdown-image-paste
   1. 截图或复制图片到系统剪切板。
   2. 在Markdown新起一行输入文件名。
   3. 点击ctrl + v将图像粘贴到markdown或rst文件中
      - 默认保存到Markdown文件相同目录下(因此要求Markdown文件应该先保存)。
      - (如果找不到图片),从新输入文件名，英文的无空格文本
4. 表格编辑(markdown-table-editor)
   - https://atom.io/packages/markdown-table-editor
   - ![markdown-table-editor](https://i.github-camo.com/c2a810dc038c3fb1a3d3373fc6ae83c51112997f/68747470733a2f2f6769746875622e636f6d2f7375736973752f6d61726b646f776e2d7461626c652d656469746f722f77696b692f696d616765732f64656d6f2e676966)

      | Name          | Description               | Keybinding  |
      | ------------- | ------------------------- | ----------- |
      | Next Cell     | Move to the next Cell     | tab         |
      | Previous Cell | Move to the previous cell | shift + tab |
      | Next Row      | Move to the next row      | enter       |
      | Escape        | Escape from table         | ESC         |

5. pdf导出(markdown-themeable-pdf、pdf-view), 比上面的pandoc轻便些，可以试试。
6. 格式化JSON(pretty-json)
   - https://atom.io/packages/pretty-json
   - ![pretty-json](https://i.github-camo.com/df2969f63f4141f94d94d6f5ab71b3a4266811b5/687474703a2f2f692e696d6775722e636f6d2f4e6434477674502e676966)
7. 格式化(atom-beautify)
   - https://atom.io/packages/atom-beautify
   - Beautify HTML, CSS, JavaScript, PHP, Python, Ruby, Java, C, C++, C#, Objective-C, CoffeeScript, TypeScript, Coldfusion, SQL, and more in Atom
8. 更多软件包，可以在官网查看，首页有[当天/本周/本月]最受欢迎的排行，看看有没有你需要的。
   - https://atom.io/packages

# 3 参考阅读
如何设置和使用Atom作为Markdown编辑器
https://www.portent.com/blog/copywriting/content-strategy/atom-markdown.htm

使用Atom打造无懈可击的Markdown编辑器
https://www.cnblogs.com/fanzhidongyzby/p/6637084.html
