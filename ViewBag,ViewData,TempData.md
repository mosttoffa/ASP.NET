# ViewBag / ViewData / TempData


<p>
ViewBag, ViewData, and TempData are used to pass data between controller and views.
ViewData and ViewBag work only for the current request, where ViewBag is dynamic and ViewData is dictionary-based.
TempData uses session internally and is used to carry messages across redirects.
For large or structured data, we always use Model or ViewModel — not ViewBag or ViewData.
</p>
<pre>
✅ ViewBag, ViewData, TempData — এগুলো কী?
নাম	                            কাজ	                                       Lifetime
ViewData	    Controller → View এ ডাটা পাঠানো	                        শুধুমাত্র current request
ViewBag	      Controller → View এ ডাটা পাঠানো (dynamic style)	        শুধুমাত্র current request
TempData	    Redirect এর পরে ডাটা ধরে রাখা (Flash Message)	          Next request পর্যন্ত
</pre>

✅ 1) ViewData
📦 Data Structure
  Dictionary type (key-value store)

✅ 2) ViewBag
📦 Data Structure
  Based on DynamicObject
  Uses ViewData internally


✅ 3) TempData
📦 Data Structure
  Backed by Session
