# The power of plain text

TL;DR. **Human-readable forms of data, and self-describing data, will outlive all other forms of data and the apps that created them**.

With plain text you can achieve a self-describing data stream that is independent of the app that created it.

Plain text doesn't mean that it's unstructured: HTML, JSON, YAML are all plain text.

If the data is in plain text, you could place it under a version control system, so that you auto keep a history of all changes.

* `diff` allows you to see the changes
* `sum` allows you to generate a checksum to be aware of accidental / malicious modification

Testing:
* plain text test data is simple to add, modify
* the output can be trivially analyzed (e.g. with shell commands / a simple script)

Plain text will always be the common standard that all parties can communicate.

References:
* The Pragmatic Programmer: Your Journey To Mastery, 20th Anniversary Edition (2nd Edition)