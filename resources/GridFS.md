**GridFS** is a specification for storing and retrieving large files, such as images, videos, or audio, in **MongoDB**, a NoSQL document database. GridFS divides a large file into smaller chunks (typically 255 kB each) and stores each chunk as a separate document within a collection. This approach allows MongoDB to handle files that exceed the document size limit of **16 MB**.