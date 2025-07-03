---
created: 2025-07-01T09:48
updated: 2025-07-03T23:20
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
>> ```dataview
>> table title as "Проект",  status
>> from "02.Working/Project"
>> where contains(status, "[x] В работе")
>> ```
>> ### Личные 
>>   ```dataview
>> table title as "Проект",  status
>> from "01.Private/Project"
>> where contains(status, "[x] В работе")
>> ```
---
> [!multi-column]
>> [!example] 📘 Дневники (последние 14)
>>   ```dataview
>> list
>> from "05.Notes/Daily"
>> where contains(tags, "дневник")
>> sort file.name desc
>> limit 14
>> ```
>
>> [!todo] 📝 Все задачи
>> ```dataview
>> table file.name as "Задача", status, priority
>> from "02.Работа"
>>where contains(file.name, "Задача")
>>sort file.mtime desc
>>```
---
> [!multi-column]
>> [!summary] Знания
>> ```dataview
>>table  
>>file.mtime as "Обновлено"
>> from "03.Information" or "03.Information/**"
>> sort file.mtime desc
>> limit 20
>> ```
>
>> [!important] Новое
>> ```dataview
>>table  
>>file.mtime as "Обновлено"
>> from "inbox" or "inbox/**"
>> sort file.mtime desc
>> limit 20
>> ```
> 


