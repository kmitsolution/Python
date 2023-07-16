# Read XML file using Python
To read an XML file in Python, you can use the built-in ElementTree module, which provides a simple way to parse and navigate XML data. Here's a step-by-step guide on how to read an XML file in Python:

### Import the ElementTree module:
```python
import xml.etree.ElementTree as ET
```
### Parse the XML file using ElementTree.parse():
```python
tree = ET.parse('example.xml')  # Replace 'example.xml' with the path to your XML file
```
### Get the root element of the XML file using getroot():
```python
root = tree.getroot()
```

Now, you can navigate and access the elements and attributes of the XML file through the root element.

## Example:

Suppose we have an XML file named "example.xml" with the following content:

```xml
<root>
    <person id="1">
        <name>John Doe</name>
        <age minor="true">10</age>
        <email>john.doe@example.com</email>
    </person>
    <person id="2">
        <name>Jane Smith</name>
        <age minor="false">25</age>
        <email>jane.smith@example.com</email>
    </person>

</root>
```

Let's read this XML file and access its content:

```python

import xml.etree.ElementTree as ET
# Parse the xml file
tree=ET.parse("example.xml")
# Get the root element
root=tree.getroot();
minorList = []
adultList = []
# print root element , root is the class of ElementTree type
for person in root.findall('person'):
    name = person.find("name").text
    age = person.find("age").text
    email = person.find("email").text
    minor = person.find("age").attrib["minor"]

    minorList.append(name) if int(age) < 18 else adultList.append(name)

    personid = person.attrib["id"]
    print("Id={0},Name={1},Age={2},Email={3}, Minor={4}".format(personid, name, age, email, minor))
print("Total Citizens=", len(minorList)+len(adultList))
print(f"This year voters={len(adultList)}")


```
### Output:

```yaml
Id=1,Name=John Doe,Age=10,Email=john.doe@example.com, Minor=true
Id=2,Name=Jane Smith,Age=25,Email=jane.smith@example.com, Minor=false
Total Citizens= 2
This year voters=1
```

In this example, we read the XML file, accessed the <person> elements, and retrieved the values of the <name>, <age>, and <email> elements for each person in the XML file. Note that the .find() method is used to find the first occurrence of the specified element, and the .text attribute gives the text content of the element.

The ElementTree module is part of the standard library in Python, so you don't need to install any additional packages to work with XML files.
