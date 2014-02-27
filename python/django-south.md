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

## Listing migrations
`python manage.py migrate --list [myapp]`

## Data migrations
`python manage.py datamigration [myapp] [my_data_migration]`