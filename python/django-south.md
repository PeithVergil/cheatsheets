Django South
============


## Installation

#### Installing South
`easy_install South`

#### Setting up Django
1.  Add **south** to the **INSTALLED_APPS**
        INSTALLED_APPS = (
            ...
            'south',
        )
2.  Create the necessary tables
        python manage.py syncdb

## Converting an app
`python manage.py convert_to_south myapp`