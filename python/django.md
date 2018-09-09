Django
======

Installation
--------------------------------------------------

```bash
pip install Django
```

Create a new Django project.

```bash
django-admin startproject myapp
```

Run the migrations.

```bash
python manage.py migrate
```

Create a super user.

```bash
python manage.py createsuperuser
```


Management commands
--------------------------------------------------

### Loading fixtures
`python manage.py loaddata [mydata].json`



######################################
# Delete the file when model is deleted from the database.
#
class ImageModel(models.Model):
    image = ImageField(...)

    def delete(self, *args, **kwargs):
        # You have to prepare what you need before deleting the model
        storage, path = self.image.storage, self.image.path

        # Delete the model before the file
        super(ImageModel, self).delete(*args, **kwargs)

        # Delete the file after the model
        storage.delete(path)

######################################
def post_delete_image_deleting(sender, instance, **kwargs):
    storage, path = instance.photo.storage, instance.photo.path
    storage.delete(path)

def pre_save_image_deleting(sender, instance, **kwargs):
    try:
        old_instance = Car.objects.get(pk = instance.pk)
    except:
        pass
    else:
        if instance.photo != old_instance.photo:
            storage = old_instance.photo.storage
            path = old_instance.photo.path
            storage.delete(path)

post_delete.connect(post_delete_image_deleting, sender=Car)
pre_save.connect(pre_save_image_deleting, sender=Car)

####################################
# sorl-thumbnail
####################################

#
# Thumbnail settings in settings.py
#
THUMBNAIL_DEBUG = True
THUMBNAIL_FORMAT = 'JPEG'
THUMBNAIL_KVSTORE = 'sorl.thumbnail.kvstores.redis_kvstore.KVStore'
THUMBNAIL_REDIS_HOST = 'localhost'
THUMBNAIL_REDIS_PORT = 6379

######################################
# Nginx+Uwsgi+Fabric.
#
http://www.abidibo.net/blog/2012/04/30/deploy-django-applications-nginx-uwsgi-virtualenv-south-git-and-fabric-part-1/
http://www.abidibo.net/blog/2012/05/23/deploy-django-applications-nginx-uwsgi-virtualenv-south-git-and-fabric-part-2/
http://www.abidibo.net/blog/2012/06/04/deploy-django-applications-nginx-uwsgi-virtualenv-south-git-and-fabric-part-3/
http://www.abidibo.net/blog/2012/06/20/deploy-django-applications-nginx-uwsgi-virtualenv-south-git-and-fabric-part-4/
http://www.abidibo.net/blog/2012/06/29/deploy-django-applications-nginx-uwsgi-virtualenv-south-git-and-fabric-part-5/
