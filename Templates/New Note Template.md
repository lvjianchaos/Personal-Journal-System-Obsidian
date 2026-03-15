---
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
alias:
tags:
source:
summary:
---
<%*
let title = tp.file.title
if (title.startsWith("未命名")) {
	title = await tp.system.prompt("Title");
}
await tp.file.rename(title)
-%>
