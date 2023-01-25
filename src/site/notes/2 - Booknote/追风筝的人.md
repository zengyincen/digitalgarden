```dataview
> list "开始阅读于 "+开始时间
> from "2 - Booknote" 
> where 开始时间>=this.开始时间 & file.name!=this.file.name
> ```