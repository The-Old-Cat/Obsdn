---
title: MOC - <% tp.frontmatter.title || "Введите тему" %>
type: MOC
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
tags: #MOC #<% tp.frontmatter.title.toLowerCase().replace(/\s+/g, '-') %>
---

# 🎯 Тема: <% tp.frontmatter.title || "Введите тему" %>

> *Последнее обновление: <% tp.date.now("DD.MM.YYYY") %>*

## 📌 Основная цель
Зачем я изучаю эту тему? Какой результат хочу получить?

- 

## 🔗 Связанные заметки
Список заметок по этой теме:

<%*
const currentTitle = tp.file.title;
const folderPath = "03.Знания/";
const files = await tp.user.listFiles(folderPath);
const relatedNotes = files.filter(file => {
  const content = app.vault.cachedMetaByFile.get(file)?.frontmatter || {};
  return content.tags && content.tags.includes(`#${currentTitle.replace(/\s+/g, '')}`);
});
tR += "- [[";
tR += relatedNotes.map(n => n.basename).join("]]\n- [[");
tR += "]]";
%>

## 🧩 Ключевые идеи
Что я уже понял? Основные концепции и подходы.

- 

## 📚 Источники
Где я черпал информацию:

- 
- 

## 🧾 Выводы и действия
Что я сделаю с этими знаниями? Как применить?

- 

## 🔄 Обновление
Когда нужно вернуться к этой теме?

- [ ] Через неделю
- [ ] Через месяц
- [ ] Через 3 месяца