# alv_util
Display deep structures and nested internal tables in ABAP.   
## 
Recently I wrote some code that dealt with deep structures and nested internal tables. To view the contents, I was using the debugger as it provides good control over nested tables also.  
But everytime putting a breakpoint and then viewing table contents in debugger was a mess. I searched SCN for something to display deep structures but couldn't find any (I did not do a very thorough search though).<br/> <br/>So I tried to develop a utility for myself that can handle the displays of deep structures and nested internal tables.
# Usage
The usage of the abap class is pretty much self-explanatory. Copy the class source code to your system, create an object of the class and call the method DISPLAY_DEEP_STRUCTURE and pass your internal table in the importing parameter. (NEW ycl_abap_util( abap_false )->display_deep_structure( deep_tab ) )
# Result Screenshots
Result Screen when helper ABAP program is Available
![Result 1](https://github.com/tewari-d/alv_util/blob/main/Result%20Screen%20when%20helper%20ABAP%20program%20is%20available.JPG?raw=true)
<br/>Result Screen when helper ABAP program is NOT Available
![Result 2](https://github.com/tewari-d/alv_util/blob/main/Result%20Screen%20when%20helper%20ABAP%20program%20is%20NOT%20available.JPG?raw=true)
# Issues / Improvements
For the code to display the results perfectly, you also need to also create an ABAP helper program 'YYR_ABAP_STATUS' with a gui status 'SALV_STANDARD'. I have attached a image of the gui status for you to copy. Basically this helper program helps in providing a GUI status to the ALV displayed by the class. <br/> If you do not want to use the helper program, you would still be able to use the class to display internal tables, but the output will not look very elegant as the class will rely on standard ALV statuses used by SALV demo programs.
# Feedback
The approach that I followed to achieve the results are very simple and brute-force, so there may be better ways to achieve the same. Hence, I would love to hear feedback and comments related to the code and the approach. Also, I am struggling to find any way to decouple the helper abap program from the class so as to have a single object performing all the tasks, any leads in that area will be very helpful.
