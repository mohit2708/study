|  No.  | [Questions]()                                                                                                              |
| :---: | -------------------------------------------------------------------------------------------------------------------------- |
|       | [Add two digit of decimal on focus out?](#add-two-digit-of-decimal-on-focus-out)                                           |
|       | [Add two digit of decimal on from the back side in run time?](#add-two-digit-of-decimal-on-from-the-back-side-in-run-time) |


### Add two digit of decimal on focus out
```javascript
<input type="text" class="two-digits valid" id="custome_price" inputmode="numeric" pattern="[0-9]*" name="custome_price" placeholder="00.00" aria-invalid="false">

$(document).ready(function() {
    $('#custome_price').on('blur', function () {
        let input = $(this).val();
        
        // Remove any non-digit characters, allowing only one decimal point
        input = input.replace(/[^0-9.]/g, '');
        
        // Only format if there's a valid number entered
        if (input && !isNaN(input)) {
            // Convert the value to a number and format it to 2 decimal places
            let formattedValue = parseFloat(input).toFixed(2);
            $(this).val(formattedValue);
        }
    });

    // Allow input but do not format until blur (when focus leaves the input)
    $('#custome_price').on('input', function () {
        let input = $(this).val();
        
        // Remove any non-digit characters except for the first decimal point
        input = input.replace(/[^0-9.]/g, '');

        // Prevent entering more than one decimal point
        if ((input.match(/\./g) || []).length > 1) {
            input = input.substring(0, input.length - 1); // Remove extra decimal points
        }

        $(this).val(input);
    });
});
```
### Add two digit of decimal on from the back side in run time
```javascript
$(document).ready(function() {
    $('#custome_price').on('input', function() {
        let inputValue = $(this).val();
        // Remove any non-numeric characters
        inputValue = inputValue.replace(/\D/g, '');
        
        if (inputValue.length > 0) {
            // Convert the number to two decimal places
            let formattedValue = (inputValue / 100).toFixed(2);
            $(this).val(formattedValue);
        } else {
            $(this).val('');
        }
    });
});
```


### Start Date and end date bootstrap calendar.
```javascript
function populateEndDate() {
    var date2 = $("#jobdate").datepicker("getDate");
    date2.setDate(date2.getDate() + 1);
    $("#jobEnddate").datepicker("setDate", date2);
    $("#jobEnddate").datepicker("option", "minDate", date2);
}

$(document).ready(function () {
    $("#jobdate").datepicker({
        // dateFormat: "dd-M-yy",
        onSelect: function (date) {
            populateEndDate();
        },
    });
    $("#jobEnddate").datepicker({
        // dateFormat: "dd-M-yy",
        minDate: 1,
        onClose: function () {
            var dt1 = $("#jobdate").datepicker("getDate");
            var dt2 = $("#jobEnddate").datepicker("getDate");
            if (dt2 <= dt1) {
                var minDate = $("#jobEnddate").datepicker("option", "minDate");
                $("#jobEnddate").datepicker("setDate", minDate);
            }
        },
    });

    // Start Date
    let mystartdate = $("#jobdate").val();
    if (mystartdate != "") {
        var mydate = new Date(mystartdate);
        $("#jobdate").datepicker("setDate", mydate);
    } else {
        $("#jobdate").datepicker("setDate", new Date());
    }

    // End Date
    let my_end_date = $("#jobEnddate").val();
    if (my_end_date != "") {
        var myenddate = new Date(my_end_date);
        $("#jobEnddate").datepicker("setDate", myenddate);
    } else {
        $("#jobEnddate").datepicker("setDate", new Date());
    }
});
```

### Add and remove the text field dynamicaly using jqury.
```javascript
$("#add-equipment").on("click", function () {
    productAddToTable();
});

function productAddToTable() {
    var equip_id        = $("#equipmId").val();
    var equi_title      = $("#equipmId").children(':selected').text();
    var equi_estimate   = $("#equip_estimate").val();

    if(equip_id == ""){
        $(".equipment_title").html('Please select the Equipment');
    }else if(equi_estimate == ""){
        $(".equipment_quantity").html('Please select Quantity');
    }else{
        $(".customcardform").append('<div class="row align-items-end mb-12 multi_select_equi">' +
        '<div class="col-md-5">' +
            '<label>Equipment Name:</label>' +
            '<input type="hidden" name="equipment_title[]" value="'+ equip_id +'">' + 
            '<input type="text" class="form-control " value="'+ equi_title +'" readonly>' + 
            '<span class="equipment_title" style="color: Red;"></span>' +
        '</div>' +
        '<div class="col-md-5">' +
            '<label>Estimate:</label>' +
            '<input type="text" class="form-control only_number" name="equipment_quantity[]" value="'+ equi_estimate +'">' +
            '<span class="equipment_quantity" style="color: Red;"></span>' +
        '</div>' +
        '<div class="col-md-2">' +
            '<label></label>' +
            '<button type="button" class="btn btn-danger w-100" id="remove_div_equipment">Remove</button>' +
        '</div>' +
        '</div>');
        $(".equipment_title").remove();
        $(".equipment_quantity").remove();
        formClear();
    }   
    
}

function formClear() {
    $("#equipmId").val("");
    $("#equip_estimate").val("");
}

$("body").on("click", "#remove_div_equipment", function () {
    $(this).parents(".multi_select_equi").remove();
})
```

### Remove the second from the input type time
```javascript
$(document).ready(function () {
    $('.job_time').each(function() {
        var timeValue = $(this).val(); // Get the current time value
        if (timeValue) {
            var formattedTime = timeValue.substr(0, 5); // Remove the seconds portion
            $(this).val(formattedTime); // Update the input value
        }
    });
});
```