---
title: Hello, TiddlyWiki
---

\procedure main()
<$text text="Hello, TiddlyWiki">
\end

\procedure main1()
<$set name="Hi" value="Hello, TiddlyWiki">
	<$text text=<<Hi>>>
</$set>
\end


<<main>>

```html
\procedure main()
<$text text="Hello, TiddlyWiki">
\end

<<main>>
```

定义方法，名为main的进程，并输出“Hello, TiddlyWiki”。
然后使用`<<main>>`调用进程。

---

<<main1>>

```html
\procedure main1()
<$set name="Hi" value="Hello, TiddlyWiki">
	<$text text=<<Hi>>>
</$set>
\end
	
<<main1>>
```

定义方法，名为main的进程，定义变量Hi，值为"Hello, TiddlyWiki"，然后输出结果，最后使用`<<main>>`调用进程。
