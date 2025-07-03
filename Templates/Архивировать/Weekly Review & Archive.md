<%*
// --- Шаг 1: Общие настройки ---
const taskFolder = "02.Работа/Задачи/";
const archiveFolder = "04.Архив/Задачи/";

// --- Шаг 2: Получаем список всех задач ---
const tasks = await tp.user.listFiles(taskFolder);

// --- Шаг 3: Архивируем каждую задачу ---
for (const task of tasks) {
  const fullPath = `${taskFolder}/${task.basename}`;
  const archivePath = `${archiveFolder}/${task.basename}`;

  // Защита от перезаписи
  let finalPath = archivePath;
  if (fs.existsSync(archivePath + ".md")) {
    const timestamp = Math.floor(Date.now() / 1000);
    finalPath = `${archiveFolder}/${task.basename}_${timestamp}`;
  }

  // Перемещаем
  await tp.file.move(finalPath, fullPath);
}

// --- Шаг 4: Перемещаем сам файл обзора ---
const reviewTitle = tp.file.title;
const newPath = "04.Архив/Обзоры/" + reviewTitle;

await tp.file.move(newPath);

// --- Шаг 5: Сообщение ---
tR += `✅ Неделя завершена. Все задачи из папки "${taskFolder}" перемещены в "${archiveFolder}".\n`;
tR += `📄 Обзор недели перемещён в: [[${newPath}]]\n\n`;
%>

# 📆 Обзор недели — <% tp.date.now("YYYY-WW") %>

## ✅ Завершённые дела
- 

## ❌ Незавершённые дела
- 

## 🚀 Прогресс по целям
- 

## 📊 Что сработало?
- 

## 🛑 Что не сработало?
- 

## 📌 План на следующую неделю
- 

## 🤔 Размышления
- 

---
> Этот файл был автоматически перемещён в папку `04.Архив/Обзоры`.