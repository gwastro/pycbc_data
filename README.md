# pycbc_data
A supplement repository to PyCBC which stores data files that might be needed in PyCBC's CI and are too large to store in PyCBC. Also acts as a backup if GWOSC is not doing what it should.

Actual files are stored by just the base filename.

Where GWOSC calls are done by URL, expecting JSON output we use the following:
```
cleaned_url = url.format(source).strip().lower()
hash_object = hashlib.md5(cleaned_url.encode('utf-8'))
hh = hash_object.hexdigest()
```
to convert the URL to the md5sum (as hex) and store the JSON output as {md5sum}.json in this directory
