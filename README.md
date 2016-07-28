# homework-5

<html>
<head>
<meta charset="UTF-8">
<title>JavaScript HTML5 Tip Calculator Application</title>
<script>
var $ = function(id){ 
    return document.getElementById(id);
}

function disable_enable() {
  document.sales_tax.total.disabled=!document.sales_tax.total.disabled
}


var billcalcultor = function () {
     //get the value of the bill subtotal and tax rate fields
    var bill = $("bill_subtotal").value;
    var tax = $("tax_rate").value;
    var salestax = $("sales_tax").value;
    var total = $("total").value;
    var isValid = true;
    
    if (bill_subtotal == "" && bill_subtotal < 1000) {
      $("bill_subtotal_error").firstChild.NodeValue = "Please enter a positive number less than 1000";
      isValid = "false";
    }

    if (tax_rate == "" && tax_rate < 25) {
        $("tax_rate_error").firstChild.NodeValue = "Please enter a positive number less than 25";
        isValid = "false";
    }

  else {
    isValid = true;
  }

var percent = salestax * .01;
var billtotal = bill_subtotal + percent + total.toFixed(2);

if (isValid) {
       $("billcalculator").submit(); 
    }
}


window.onload = function () {
    $("calculate").onclick = calculate;
    $("clear").onclick = reset();
    $("billcalculator").focus();  
    
} 


</script>
</head>
<body>

<h2>Bill Calculator</h2>
<form id="billcalculator" name="billcalculator" method="get">
Bill Subtotal:
<input type="text" id="bill_subtotal">
<span id="bill_subtotal_error">Enter Subtotal</span><br>
Tax Rate: 
<input type="text" id="tax_rate">
<span id="tax_rate_error">Enter sales tax rate (e.g. 9.5)</span><br>
Sales Tax:
<input type="text" id="sales_tax" disabled="disabled"><br>
Total:
<input type="text" id="total" disabled="disabled"><br>
<input type="button" id="calculate" value="Calculate">&nbsp;
<input type="button" id="clear" value="Clear">
</form>
</body>
</html>
