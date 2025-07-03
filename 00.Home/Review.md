---
created: 2025-07-01T09:48
updated: 2025-07-03T11:20
cssclasses:
  - dashboard
---

## 📊 Хранилище

- ### 🗄️ Недавние обновления файлов  
`$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(4).file.link)`  
- ### 🔖 Избранное:      `$=dv.list(dv.pages('#favorite').sort(f=>f.file.name,"desc").limit(4).file.link)`  
- ### 〽️ Статистика  
	-  Количество файлов: `$=dv.pages().length`  
	-  Личные записи: `$=dv.pages('"01.Личный"').length`

## Актуальное

> [!multi-column]
>> [!done] Проекты
>> ### Рабочие 
>>   ```dataview
>> table file.name as "Проект", status
>> from "02.Working/Project"
>> where contains(status, "[x] В работе")
>> ```
>> ### Личные 
>>   ```dataview
>> table file.name as "Проект", status
>> from "01.Private/Project"
>> where contains(status, "[x] В работе")
>> ```
>
>> [!example] 📘 Дневники (последние 14)
>>   ```dataview
>> list
>> from "05.Notes/Daily"
>> where contains(tags, "дневник")
>> sort file.name desc
>> limit 14
>> ```
----
> [!multi-column]
>> [!todo] 📝 Все задачи
>> ```dataview
>> table file.name as "Задача", status, priority
>> from "02.Работа"
>>where contains(file.name, "Задача")
>>sort file.mtime desc
>>```
>
>> [!summary] 📝 Новое
>> ```dataview
>>table 
>>   file.link as "Файл",
> >  file.mtime as "Обновлено"
>> from "inbox" or "inbox/**"
>> sort file.mtime desc
>> limit 20
>> ```
> 


