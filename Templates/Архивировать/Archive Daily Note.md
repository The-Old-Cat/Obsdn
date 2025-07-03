<%*
// Получаем название текущей заметки (дневника)
const title = tp.file.title;

// Формируем путь в архиве
const archivePath = "04.Архив/" + title;

// Проверяем, существует ли файл с таким названием в архиве
const fs = require("fs");
let finalPath = archivePath;

if (fs.existsSync(archivePath + ".md")) {
  const timestamp = Math.floor(Date.now() / 1000);
  finalPath = `04.Архив/${title}_${timestamp}`;
}

// Перемещаем файл
await tp.file.move(finalPath);

// Выводим сообщение
tR += `✅ Дневник "${title}" перемещён в [[04.Архив]]\n\n`;
%>

# 📖 Дневник за <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD") %> завершён

- [x] Завершено: <% tp.date.now("YYYY-MM-DD HH:mm") %>
- [x] Перемещён в папку [[04.Архив]]

📌 Новое расположение: `[[<% finalPath %>]]`

---
> Этот файл был автоматически архивирован после завершения дня.