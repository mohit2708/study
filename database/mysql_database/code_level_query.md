### Update remaing days startdate - enddate
```sql
UPDATE advance_bookings
SET remaining_days = DATEDIFF('2025-01-31', CURDATE()), end_date = '2025-01-31'
WHERE id = 4529;

# End date dynamic
UPDATE advance_bookings
SET remaining_days = DATEDIFF(end_date, CURDATE()), end_date = end_date
WHERE id = 4529;
```

### count phone number  
```sql
SELECT phone, count(phone) as total_phone FROM `users` WHERE role_id = 4 group by phone having count(phone) > 1;
```