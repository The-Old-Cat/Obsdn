---
title: Заметка — <% tp.file.title %>
created: <% tp.date.now("HH:mm Do MMMM YYYY") %>
type: note
tags: 
updated: <% tp.file.last_modified_date("HH:mm Do MMMM YYYY") %>
---

# 📝 Заметка: <% tp.frontmatter.title %>

<% tp.file.cursor() %>