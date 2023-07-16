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

## Manipulate XML file using Python
Let's consider an advanced example of working with XML in Python. In this example, we will create an XML file representing a simple playlist with songs and their details, and then we will read and manipulate the XML data using the xml.etree.ElementTree module.

Creating the XML File (playlist.xml):
```xml
<playlist>
    <song>
        <title>Song 1</title>
        <artist>Artist 1</artist>
        <duration>3:45</duration>
    </song>
    <song>
        <title>Song 2</title>
        <artist>Artist 2</artist>
        <duration>4:10</duration>
    </song>
    <song>
        <title>Song 3</title>
        <artist>Artist 3</artist>
        <duration>5:15</duration>
    </song>
</playlist>
```

## Reading and Manipulating the XML File:
```python
import xml.etree.ElementTree as ET

# Read the XML file
file_path = 'playlist.xml'
tree = ET.parse(file_path)
root = tree.getroot()

# Print the playlist
print("Playlist:")
for song in root.findall('song'):
    title = song.find('title').text
    artist = song.find('artist').text
    duration = song.find('duration').text
    print(f"Title: {title}, Artist: {artist}, Duration: {duration}")

# Add a new song to the playlist
new_song = ET.Element('song')
new_title = ET.SubElement(new_song, 'title')
new_title.text = 'New Song'
new_artist = ET.SubElement(new_song, 'artist')
new_artist.text = 'New Artist'
new_duration = ET.SubElement(new_song, 'duration')
new_duration.text = '2:30'
root.append(new_song)

# Update the duration of the first song
first_song = root.find('song')
first_song.find('duration').text = '3:50'

# Delete the second song from the playlist
second_song = root.findall('song')[1]
root.remove(second_song)

# Write the updated XML to a new file
updated_file_path = 'updated_playlist.xml'
updated_tree = ET.ElementTree(root)
updated_tree.write(updated_file_path)

print("\nUpdated Playlist:")
for song in root.findall('song'):
    title = song.find('title').text
    artist = song.find('artist').text
    duration = song.find('duration').text
    print(f"Title: {title}, Artist: {artist}, Duration: {duration}")

print("XML data has been updated and written to 'updated_playlist.xml'.")
```

In this example, we first read the XML data from the "playlist.xml" file, then print the playlist details. Next, we add a new song, update the duration of the first song, and delete the second song from the playlist. Finally, we write the updated XML data to a new file called "updated_playlist.xml" and print the updated playlist details.


