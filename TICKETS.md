# QA has submitted the following tickets


## Customer Orders Table
### QA Notes
When viewing the Customer Orders table, the times don't always display correctly. They're in 24-hour format when they should be in 12-hour format with AM/PM displayed.

Additionally, time should display in (H)H:MM format, but currently 12:07 displays as 12:7.

### Dev Notes / Response
Utilized toLocaleString() to format the Date object into the proper format. en-US locale follows 12-hour format. 

Another possible approach could be to manually check if the hours >= 12 to determine AM or PM, and perform operations to convert 24-hour value to 12 hour.

For a larger project I would probably utilize a library like Moment.js, because it would provide much more utility and flexibility in the formatting of said dates. A larger project may utilize different formats or require format changes down the line.


---


## Customer Order Details
### QA Notes
There seems to be an issue with total price sometimes. On some order details, the total price is displaying values after the penny.

### Dev Notes / Response
Prices are stored as integers (x100 of the 'cost'). To display the proper price, division by 100 is required. The component originally would divide each value by 100 before adding, which means it is adding many decimals together and potentially running into floating-point issues.

We can avoid this can sum everything as its integer value, and then divide the final integer total by 100 to get it into our desired format.

---


## Delete a Customer Order
### QA Notes
I'm currently unable to delete a customer order. Every time I click the "Delete" button from the Customer Orders table, I get a white screen.

### Dev Notes / Response


---


## Other