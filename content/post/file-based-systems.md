---
Title: Files should be back!
Date: 2012-06-13
---

The core concept of document-oriented databases is that we have some a priori knowledge about a data structure of documents we store. For instance, in CouchDB or MongoDB we are aware that any document is an associative array. This knowledge allows us to query document sets with something like `(get all documents where 'age' attribute is 18)` or `(get all documents where 'published' is True)`.

## File system is the best document DB ever

The concept of scriptogr.am got me thinking that a file system is a perfect document-oriented database. Not only it stores documents, reads/writes them by `id`, it has the most usable user interface ever - provided by the operating system. There are tons of cool tools for working with files and files remain perfectly interpretable no matter what happens to your  whole system.

The only thing you need to add to a file system to make a document-oriented database of it is adding this a priori structure, allowing queries. In scriptogr.am it the file header containing metadata of a post. Every scriptogr.am post has such a header, so we can query posts with certain tags or sort them by date. To make queries work fast, of course, we will need to maintain some extra data structures (like b-trees) on top of posts folder, and index them. But our files with metadata remain completely unaffected by the way we make queries on them, it is  only the content they contain.

Let us try to generalize a bit. Say we have some folder of files (text files, spreadsheets, anything *parsable*). We also have some a priori knowledge about the structure of a *any* document in that folder (for example, we know that the first line of a text file is a title, or column names in spreadsheets). This knowledge allows us to build a query system over the documents in that folder, and use this system to build useful services for navigating, searching or analyzing these files somehow.

Access control is important. The limitation of a file system is you only can make restrictions to the file as a whole - the same way it works in document-oriented databases. If you need to build a service that has several access levels, you need to partition your files accordingly.

Basically, from a query level on top of a document store you need:

* Document validation, to make sure every file you encounter in a folder has a right structure
* Data mapping, a procedure of extracting the queriable data out of a document
* Query engine, to make queries on mapped data
* Maintaining indexes, to make queries fast. Though, it is, obviously, not required to make queries.

## Using Couch

From all NoSQL databases I only have experience with CouchDB, but by far the most intuitive way I can imagine querying is:

1. Data mapping procedure produces JSON document with queryable data for every document in the folder.
2. Query engine runs map-reduce queries over these JSON documents.

So, it appears that CouchDB is a solution for storing queryable data: it does all that querying and indexing stuff. We can now store all the queryable data in it, and maintain proper mapping between queryable data from documents and documents themselves. Once a document in a folder gets modified, we need to modify it's mapped queryable data accordingly. If we do that, CouchDB will take care of the rest and allow queries on this data.

## Roundup

It is possible to build some sort of toolkit for turning any collection of structured files into document-oriented database. For a particular collection one needs to implement a routine that:

1. Checks if a file has a proper structure
2. In case it does, extracts the queryable information from it in JSON format
3. Pushed JSON data to CouchDB (to a document with `id` matching the filename)

I'm pretty sure that CouchDB is not the solution that fits here. I also need to dig into dropbox's API docs to understand how to implement this routine using dropbox. Right now I'm considering an ussue tracker application as a good 'proof of concept' idea for this project. I'll try to think about it some more tomorrow, maybe come up with some more implementation ideas.
