# ViewBag / ViewData / TempData


<p>
ViewBag, ViewData, and TempData are used to pass data between controller and views.
ViewData and ViewBag work only for the current request, where ViewBag is dynamic and ViewData is dictionary-based.
TempData uses session internally and is used to carry messages across redirects.
For large or structured data, we always use Model or ViewModel — not ViewBag or ViewData.
</p>

✅ <b>ViewBag, ViewData, TempData — এগুলো কী? </b>
<pre>
নাম	                            কাজ	                                       Lifetime
------------------------------------------------------------------------------------------------
ViewData	    Controller → View এ ডাটা পাঠানো	                        শুধুমাত্র current request
ViewBag	      Controller → View এ ডাটা পাঠানো (dynamic style)	        শুধুমাত্র current request
TempData	    Redirect এর পরে ডাটা ধরে রাখা (Flash Message)	          Next request পর্যন্ত
</pre>

✅ 1) ViewData <br> 
📦 Data Structure : <br>
    - Dictionary type (key-value store) <br>

✅ 2) ViewBag <br> 
📦 Data Structure : <br> 
    - Based on DynamicObject <br> 
    - Uses ViewData internally <br> 

✅ 3) TempData  <br> 
📦 Data Structure : <br> 
    - Backed by Session
