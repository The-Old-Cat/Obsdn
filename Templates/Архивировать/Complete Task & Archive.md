<%*
// Получаем название текущей заметки
const title = tp.file.title;

// Путь к архиву
const archivePath = "04.Архив/" + title;

// Проверяем, существует ли файл с таким названием в архиве
const fs = require("fs");
let finalPath = archivePath;

if (fs.existsSync(archivePath + ".md")) {
  // Если существует — добавляем временную метку
  const timestamp = Math.floor(Date.now() / 1000);
  finalPath = `04.Архив/${title}_${timestamp}`;
}

// Перемещаем файл
await tp.file.move(finalPath);

// Выводим сообщение в заметку
tR += `✅ Задача "${title}" завершена и перемещена в [[04.Архив]]\n\n`;
%>

# ✅ Задача завершена

- [x] Эта задача была завершена <% tp.date.now("YYYY-MM-DD") %>
- [x] Перемещена в папку [[04.Архив]]

📌 Вы можете найти её по пути: `[[<% finalPath %>]]`

---
> Этот файл создан автоматически после завершения задачи.