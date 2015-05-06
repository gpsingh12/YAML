YAML
-----
While having learnt about flat text, json and pickle this week, I would like to
provide some information on another data storage known as YAML.  YAML is
superset of json. It is visually easier to look at. In fact the YAML homepage
is itself valid YAML, yet it is easy for a human to read. YAML has the ability
to reference other items within a YAML file using "anchors." Thus it can handle
relational information as one might find in a MySQL database. YAML is more
robust about embedding other serialization formats such as JSON or XML within a
YAML file. YAML represents simple data types & structures in a language-portable
manner whereas pickle can represent complex structures, but in a non-language
-portable manner. YAML has language-neutral formats that can represent primitive
types (int, string, etc.) well, and is highly portable between languages. The
constructs within YAML such as mappings, sequences, and scalars all mesh nicely
with existing Python data types like dictionaries, lists, strings, and integers.
It is not only the markup language, as the name suggests Yet Another Markup
Language, it is a human friendly data serialization standard for all programming
languages. It has the advantage of leaning towards dynamic languages. It's also
fully unicode-enabled, which should make happy a lot of people who are normally
worried about UTF-8.

Reading the yaml
^^^^^^^^^^^^^^^
>>> import yaml
>>> document = """
  a: 1
  b:
    c: 3
    d: 4
"""
>>> print yaml.dump(yaml.load(document))

a: 1
b: {c: 3, d: 4}

>>> 

Writing the yaml
^^^^^^^^^^^^^^^
>>> 
>>> import yaml
>>> data = dict(
    A = 'a',
    B = dict(
        C = 'c',
        D = 'd',
        E = 'e',
    )
)
>>> with open('data.yml', 'w') as outfile:
	outfile.write(yaml.dump(data, default_flow_style=True))
A: a
B: {C: c, D: d, E: e}


The default_flow_style=True parameter is necessary to produce the format you want (flow style in this case)


