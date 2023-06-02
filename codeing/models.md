### How to create model Integrate Existing DBs with Django?
```python
python manage.py inspectdb > blog_app/models.py
```


### Database seeding fixture file
```python
# it is commend for export the data from the database
python manage.py dumpdata your_app_name.model_name  > country.json

# for import the data in database.
1. we create the folder "fixtures" name in app (OR)
    cd your_app_name
    mkdir fixtures
2. create the json file in this folder and creat the data in this format below.
    country.json
[
    {
      "model": "ajaxCountryStateCity.countries",
      "pk": 1,
      "fields": {
        "shortname": "in",
        "name": "India",
        "phonecode": 91
      }
    },
    {
      "model": "ajaxCountryStateCity.countries",
      "pk": 2,
      "fields": {
        "shortname": "us",
        "name": "usa",
        "phonecode": 65
      }
    },
    {
      "model": "ajaxCountryStateCity.countries",
      "pk": 3,
      "fields": {
        "shortname": "The",
        "name": "gfj",
        "phonecode": 354
      }
    }
]
python manage.py loaddata city.json (OR)
python manage.py loaddata your_app_name/fixtures/city.json


note:- if error add code in model file.
class Cities(models.Model):
    name = models.CharField(max_length=30)
    state_id = models.IntegerField()
    class Meta:
            app_label = 'ajaxCountryStateCity'
```