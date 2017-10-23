#  Benefits of using your ORCID iD

20 Minutes

---

## Learning Objectives

* See how ORCID can be used as a central storage location for your works
* Experience integrating your ORCID account with another service
* Advanced: Use the ORCID API to extract works from your profile

There are lots of services that integrate with ORCID.  Go to
[scincv](https://www.ncbi.nlm.nih.gov/sciencv/) and set up an account.  Other
integrations include [impactstory](https://profiles.impactstory.org/) (also
requires a Twitter account) and [growKudos](https://www.growkudos.com/) 


## Advanced: Basic intro to the ORCID API

ORCID is an open resource, which means you have complete control of and access to your data.
We've already seen how you can use the privacy controls to limit access to any
part of your ORCID profile.  For this example to work your profile will have to
be public, because we're going to access the information via the public API.
An API is a way for computer systems to interact.  

In this example we want to get a text version of all the works in our ORCID
profile.

We're going to use orcidtoold, a package designed to make using the ORCID API
easier.  Download
[orcidtools](https://github.com/caltechlibrary/orcidtools/releases) for your
operating system, unzip the download, and move the executible (under /bin) to a
location on your PATH.  If you don't know your path, open a terminal window and
type 'echo $PATH'.  You can add a location to your path (like HOME/bin) by typing 'export
PATH=$HOME/bin:$PATH'.

Now, we have to get API access.  Go to [developer
tools](https://orcid.org/developer-tools) and click on "Register for the free
ORCID public API".  You'll have to agree to the terms of service.  The API can
do much more than we're going to use today.  To get access, we have to make up
an application.  You can enter things like "Test" in all the fields.  Click the
"Google Auth" line with the plus sign, and then click the save button (the
black circle).  Click the "Show details" button to see our identifying
information.

Now open up a terminal window.  We need to enter the information we just set by
typing

```
export ORCID_CLIENT_ID="PASTE_ID_HERE"
export ORCID_CLIENT_SECRET="PASTE_SECRET_HERE"
export ORCID_API_URL="https://pub.orcid.org"
```
 
### Searching
We can search using the ORCID API.  Let's try to look at affilliations

```
orcid -search 'affiliation-org-name:(Caltech OR "California Institute of
Technology")'

orcid -search 'affiliation-org-name:("Jet Propulsion Laboratory" OR "NASA Jet
Propulsion Laboratory")'

orcid -search 'email:*jpl.nasa.gov'

orcid -search 'email:*caltech.edu'


```

The full documentation for searching is available at
[https://members.orcid.org/api/tutorial/search-orcid-registry](https://members.orcid.org/api/tutorial/search-orcid-registry)

### Exporting Data
 
You can also use the API to get data from a specific profile.  We want to get the works from our
profile.  Type (replacing the ORCID number)

```
orcid -works 0000-0001-9266-5146 > tmorrell.json
```

This is all the information in your profile in a difficult to read format
called json.  We want to make this pretty. Open the file (tmorrell.json in the
example) in atom and use PrettyJSON.  

We can use [mkpage](https://github.com/caltechlibrary/mkpage) and a 
[template]
(https://github.com/caltechlibrary/orcidtools/blob/master/templates/orcid2txt.tmpl) to
format the results as a text list of citations.

```
mkpage 'data=tmorrell.json' orcid2txt.tmpl
```

Previous: [Getting Started with OrCiD](00-orcid-profile.html)
