在终端中修改文件名，可以使用 `mv` 命令。以下是详细的使用方法：

---

### **基本语法**
```bash
mv [旧文件名] [新文件名]
```

### **示例操作**
#### 1. 修改单个文件名
将 `oldname.txt` 改为 `newname.txt`：
```bash
mv oldname.txt newname.txt
```

#### 2. 修改文件夹名
将文件夹 `old_folder` 改为 `new_folder`：
```bash
mv old_folder new_folder
```

---

### **批量修改文件名**
如果需要批量修改文件名，可以结合 `for` 循环或其他工具。

#### 示例 1：修改扩展名
将所有 `.txt` 文件改为 `.md` 文件：
```bash
for file in *.txt; do
  mv "$file" "${file%.txt}.md"
done
```

#### 示例 2：添加前缀
为所有 `.txt` 文件添加前缀 `new_`：
```bash
for file in *.txt; do
  mv "$file" "new_$file"
done
```

#### 示例 3：批量替换文件名中的特定字符
将所有文件名中的 `_` 替换为 `-`：
```bash
for file in *_*; do
  mv "$file" "${file//_/-}"
done
```

---

### **常见错误处理**
1. **权限不足**：
   - 如果文件需要管理员权限修改：
     ```bash
     sudo mv oldname.txt newname.txt
     ```

2. **文件或目录不存在**：
   - 确保路径正确。如果文件在其他目录：
     ```bash
     mv /path/to/oldname.txt /path/to/newname.txt
     ```

---

### **交互式重命名工具（可选）**
对于更复杂的重命名需求，可以使用 `rename` 工具。

#### 安装 `rename`：
- 在 Debian/Ubuntu：
  ```bash
  sudo apt install rename
  ```
- 在 macOS（使用 Homebrew）：
  ```bash
  brew install rename
  ```

#### 示例：批量替换字符串
将所有 `.txt` 文件的扩展名改为 `.log`：
```bash
rename 's/\.txt$/.log/' *.txt
```

---

通过以上方法，你可以高效地在终端中修改文件名。如果有更具体的场景需求，可以告诉我，我可以为你定制解决方案！ 😊
