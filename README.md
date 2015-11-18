# Django modules for SAE

in project `settings.py` add the following code

```python
DEPLOYED = True
try:
    import sae.const
except ImportError:
    DEPLOYED = False

if DEPLOYED:
    DEFAULT_FILE_STORAGE = 'django_sae.files.storage.SAEStorage'
    SAE_DEFAULT_STORAGE_DOMAIN_NAME = 'imgs'
else:
    DEFAULT_FILE_STORAGE = 'django.core.files.storage.FileSystemStorage'
```
