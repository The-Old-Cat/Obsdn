---
title: Обзор <% tp.date.now("YYYY-WW") %> недели
date: <% tp.date.now("YYYY-MM-DD") %>
type: weekly-review
tags:
  - "#обзорнедели"
  - "#план"
---

# 🗓️ <% tp.frontmatter.title %> — <% tp.date.now("WW", 0, tp.file.title, "YYYY-WW") %> неделя

<% tp.date.now("dddd, D MMMM YYYY") %>
<%*

const title =  await tp.date.now(" DD-MM-YYYY");;

await tp.file.rename( title );
%>
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

## 🤔 Выводы и размышления
- 