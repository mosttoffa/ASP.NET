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

<p>
✅ সহজ ভাষায় ভাবুন <br>
    ViewData = ব্যাগ যেখানে key-value আকারে ডাটা রাখি (Dictionary) <br>
    ViewBag = একই ব্যাগ, কিন্তু property আকারে access (dynamic) <br>
    TempData = ছোট storage যা redirect এর পরেও একবার ডাটা ধরে রাখে (Session)
</p>
✅ কেন এগুলো দরকার?  <br> 
🎯 মূল উদ্দেশ্য <br> 
<pre>
কবে দরকার	                            কোনটা ব্যবহার
------------------------------------------------------------------
View page এ ছোট ডাটা পাঠাতে	            ViewData / ViewBag
Redirect এর পরে message দেখাতে	        TempData
বড় ডাটা (list/model) পাঠাতে	            Model/ViewModel ✅ Best way
</pre> 
✅ Real Life Example : <br>
<pre> 
        Scenario	                             Tool
------------------------------------------------------------------------
Page Title পাঠানো	                        ViewBag.Title
Success message after Save → redirect	    TempData["Success"]
Dropdown data পাঠানো (কম ডাটা হলে)	        ViewBag.CategoryList
Product list পাঠানো	                        Model ✅
</pre>

✅ 1) ViewBag <br> 
📦 Data Structure : <br> 
    - Based on DynamicObject <br> 
    - Uses ViewData internally <br> 
    
✅ 2) ViewData <br> 
📦 Data Structure : <br>
    - Dictionary type (key-value store) <br>
    - Type: 
    
```cs
    public class ViewDataDictionary : Dictionary<string, object>
```
    - অর্থাৎ ViewData মূলত Dictionary<string, object> — key string, value object. 
🔷 সুবিধা (Advantages): 
    Simple key-value data pass - 


✅ 3) TempData  <br> 
📦 Data Structure : <br> 
    - Backed by Session
