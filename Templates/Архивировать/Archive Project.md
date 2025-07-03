<%*
// Получаем название текущего проекта
const title = tp.file.title;

// Формируем путь в архиве
const archivePath = "04.Архив/Проекты/" + title;

// Проверяем, существует ли файл с таким названием в архиве
const fs = require("fs");
let finalPath = archivePath;

if (fs.existsSync(archivePath + ".md")) {
  const timestamp = Math.floor(Date.now() / 1000);
  finalPath = `04.Архив/Проекты/${title}_${timestamp}`;
}

// Перемещаем файл
await tp.file.move(finalPath);

// Выводим сообщение
tR += `✅ Проект "${title}" перемещён в [[04.Архив/Проекты]]\n\n`;
%>

# 🧩 Проект завершён: <% tp.frontmatter.title || "Введите название" %>

- [x] Статус: Завершён
- [x] Дата завершения: <% tp.date.now("YYYY-MM-DD") %>
- [x] Перемещён в папку [[04.Архив/Проекты]]

📌 Новое расположение: `[[<% finalPath %>]]`

---
> Этот файл был автоматически архивирован после завершения проекта.