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

# Visual Studio Code (VS Code)

Visual Studio Code (VS Code) is a **free**, **lightweight**, yet **powerful** code editor that supports a wide range of languages and extensions. Many trading strategy developers rely on VS Code for its **intuitive interface**, **Git integration**, and **extensive customization** options, making it easy to work on `.md` files, scripts (EasyLanguage, C#, Python, etc.), and more—**all in one place**.

---

## 1. Installation & Setup

1. **Download & Install**  
   - Visit the [official VS Code website](https://code.visualstudio.com/) and choose your operating system (Windows, macOS, or Linux).  
   - Run the installer and follow the on-screen instructions.

2. **Initial Launch**  
   - Open Visual Studio Code.  
   - You’ll be greeted with a “Welcome” or “Get Started” screen that includes tutorials and extension recommendations.

3. **Open Your Project Folder**  
   - Go to **File → Open Folder** (or **File → Open** on macOS) and select the local folder that contains your GitHub repository.  
   - Now you can explore and modify all `.md` files, strategy code, and other resources.

---

## 2. Recommended Extensions

While VS Code works well out of the box, adding a few extensions can significantly improve your workflow:

1. **GitHub Pull Requests and Issues**  
   - Integrates GitHub directly into VS Code, letting you manage pull requests, issues, and code reviews without leaving the editor.

2. **Markdown All in One**  
   - Provides a live preview, shortcuts, and syntax helpers for Markdown files (`.md`).  
   - Great for quickly drafting or editing documentation.

3. **EasyLanguage** (Optional)  
   - Although not an official extension, there are some community-driven options that offer EasyLanguage syntax highlighting for TradeStation or MultiCharts code.

4. **C#** (for NinjaTrader or general .NET development)  
   - If you’re coding strategies in C#, the official Microsoft C# extension provides intellisense, debugging, and more.

5. **Bracket Pair Colorizer 2** (or similar)  
   - Makes nested code blocks easier to read by coloring matching brackets.

6. **Indent-Rainbow**  
   - Highlights indentation levels in different colors, making deeply nested code blocks more manageable.

7. **ESLint / StyleLint / Prettier**  
   - If you use JavaScript/TypeScript or want a consistent code style, these linting and formatting tools keep your code clean.

---

## 3. Git Integration

VS Code has built-in Git functionality that pairs nicely with **GitHub Desktop** or direct Git usage:

1. **Source Control Panel**  
   - Click the **Source Control** icon in the Activity Bar (the sidebar icons on the left).  
   - VS Code detects your Git repository automatically, showing changed files and allowing you to stage/commit.

2. **Branches & Commits**  
   - VS Code can switch branches, create commits, and push/pull changes.  
   - For more complex Git operations (resolving conflicts, rebasing), you might still prefer GitHub Desktop or the command line.

3. **Extensions for GitHub**  
   - You can install the **GitHub Pull Requests and Issues** extension to open, review, and merge pull requests directly within VS Code.

---

## 4. Editing & Navigation Tips

1. **Command Palette**  
   - Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS) to access the **Command Palette**.  
   - Type commands like “git,” “markdown preview,” or “format document” to execute them quickly.

2. **Split Editing**  
   - Right-click on a file tab and select **Split** to view multiple files side by side—handy for comparing `.md` content with code.

3. **Go to Symbol / Definition**  
   - For languages like C# or Python, VS Code can jump to definitions of functions or variables.  
   - Press `F12` or use the Command Palette to “Go to Definition.”

4. **Markdown Preview**  
   - In a `.md` file, press `Ctrl+Shift+V` (Windows) or `Cmd+Shift+V` (macOS) to open a live preview.  
   - The “Markdown All in One” extension offers additional preview features and shortcuts.

5. **Integrated Terminal**  
   - **View → Terminal** (or `Ctrl+Shift+` on Windows/Linux, `Cmd+Shift+` on macOS) opens a terminal at the bottom.  
   - Run Git commands, Python scripts, or other utilities directly inside VS Code.

---

## 5. Working with Code (Examples)

### 5.1 TradeStation / MultiCharts (EasyLanguage)

Although there’s no official EasyLanguage extension from TradeStation or MultiCharts, you can:

- Use a **generic syntax highlighting** extension or search the VS Code Marketplace for **“EasyLanguage”**.  
- Edit `.eld` or `.els` files offline.  
- Copy and paste code into the TradeStation/MultiCharts editor to compile.

### 5.2 NinjaTrader (C#)

- Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) by Microsoft.  
- Open `.cs` files from your NinjaTrader scripts folder.  
- Code completion, debugging, and refactor tools can significantly speed up development.

### 5.3 Python or R for Data Analysis

- Install the relevant extension (`Python`, `R`) from the VS Code Marketplace.  
- Use integrated Jupyter Notebook support or the built-in terminal for data crunching.

---

## 6. Customization & Settings

1. **User & Workspace Settings**  
   - Go to **File → Preferences → Settings** (Windows/Linux) or **Code → Preferences → Settings** (macOS).  
   - Adjust editor preferences like font size, theme, auto-save, format on save, etc.

2. **Keybindings**  
   - If you have a preferred keybinding scheme (like Sublime or Vim), you can install **keymap extensions** that replicate those shortcuts.

3. **Themes**  
   - VS Code offers many built-in themes, and you can install more from the Marketplace.  
   - Popular ones include **Dark+, Monokai, One Dark Pro**, etc.

---

## 7. Troubleshooting

1. **Code Not Recognized**  
   - If your language syntax highlighting or intellisense isn’t working, confirm the correct extension is installed and enabled.  
   - Check that VS Code recognizes the file extension (e.g., `.cs`, `.py`, `.md`).

2. **Git Integration Issues**  
   - Ensure you have Git installed globally and configured.  
   - Sometimes you need to re-authenticate with GitHub if the credentials expire.

3. **Conflicts with Other Tools**  
   - If you simultaneously use GitHub Desktop or a separate IDE, be mindful of open files in multiple apps.  
   - Keep your local environment consistent by pulling updates frequently and resolving merges promptly.

---

## 8. Conclusion

Visual Studio Code is a **versatile, highly customizable** editor that integrates seamlessly with Git, GitHub, and various programming languages. By adding a few **key extensions** and exploring its powerful **navigation** and **debugging** features, you can streamline your entire workflow—from writing code and documentation to managing version control directly in one environment.

**Resources**  
- [VS Code Official Docs](https://code.visualstudio.com/docs)  
- [VS Code Marketplace](https://marketplace.visualstudio.com/vscode) for extensions  
- [Getting Started with Git](https://git-scm.com/book/en/v2) (if you need deeper Git knowledge)

Use VS Code’s built-in Git integration or **GitHub Pull Requests and Issues** extension to collaborate effectively with your team, ensuring each trading strategy iteration is documented, tested, and easily retrievable.