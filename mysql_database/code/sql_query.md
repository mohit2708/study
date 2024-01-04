###
```sql
SELECT job_id, equipmentTitle, entery_by_qty,
    SUM(CASE WHEN entery_by = 'delivery' OR entery_by = 'cal_delivery' THEN entery_by_qty ELSE 0 END) AS total_delivery_qty,
    SUM(CASE WHEN entery_by = 'pickup' THEN entery_by_qty ELSE 0 END) AS total_pickup_qty
FROM job_equipment
WHERE job_id = 46 AND entery_by != 'admin'
GROUP BY equipmentTitle, sub_location_id
```

### Check the time slot between start time and end time
```sql
SELECT * FROM `bookings` WHERE ((`start_time` <='17:25:00' and `end_time` >='17:25:00') or (`start_time` <='18:05:00' and `end_time` >='18:05:00')) and (created_at like '2023-09-22%' )
```