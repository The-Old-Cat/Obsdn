---
title: Дневник за <% tp.date.now(" D MMMM YYYY") %>
date: <% tp.date.now("D MMMM YYYY") %>
type: daily
tags:
  - "#дневник"
  - "#ежедневно"
---
# 📖<% tp.frontmatter.title %>
<% tp.date.now("dddd, D MMMM YYYY") %>
<%*
const title = await tp.date.now(" DD-MM-YYYY");
await tp.file.rename(title);
%>

## 🧠 Настроение дня
- [ ] Отличное  
- [ ] Хорошее  
- [ ] Обычное  
- [ ] Плохое  

## 🎯 Цели дня
- [ ] 
- [ ] 
- [ ]

## 📝 Что произошло?
- 

## 💡 Размышления
- 

## 🔁 Что повторить завтра?
- 