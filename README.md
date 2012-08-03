Appetizer
=========

A flexible configuration manager for Python

Based on a [blog post by Sam&Max](sametmax.com/votre-avis-sur-ce-projet-de-lib-de-gestion-de-configuration-python/)

Expected behaviour
------------------

<pre><code>
from appetizer import Configuration, Schema
 
# Free access to the configuration, no constraint:
config1 = Configuration('/path/to/config/file.json')
print config1.url
config1.answer = 42
 
# Access using a Schema:
class MySchema(Schema):
    nom = TextField()
    age = IntegerField()
 
config2 = Configuration('http://data.okso.me/config.iso', schema=MySchema())
config2.name = 'Bob'
# The following commands will fail:
config2.name = 34
config2.nickame = 'Marley'
config2.age = 3.2
</code></pre>