`$("#transport_province_1")` is dropdown selector and has `onchange` event that trigger other dropdown.

`selected_stations[0].region1_id` is the value of the data
```javascript
$("#transport_province_1").val('{{ selected_stations[0].region1_id }}').change();
```
