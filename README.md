# NN
AI
.

////// app script
function doGet(e) {
  
  return HtmlService.createHtmlOutputFromFile("index");
}

function saveData(name,phone){
  var ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  ss.appendRow([new Date(),name,"'"+phone]);

}
/////////html
<!DOCTYPE html>
<html>
  <head>
    <base target="_top">
  </head>
  <body>
    <h1>ระบบบันทึกข้อมูลด้วย Web App</h1>
    <label>ชื่อ สกุล:</label><input type="text" id="username">
    <label>เบอร์โทร:</label><input type="text" id="tel"><p>
    
    <button id = "btn">บันทึกข้อมูล</button>
    
    <script>
    document.getElementById("btn").addEventListener("click",submit);
    
    function submit(){
    var name =  document.getElementById("username").value;
    var phone =  document.getElementById("tel").value;
    google.script.run.saveData(name,phone);
    document.getElementById("username").value="";
    document.getElementById("tel").value="";
    
    }
    </script>
    
  </body>
</html>