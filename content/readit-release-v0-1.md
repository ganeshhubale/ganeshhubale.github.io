Title: Announcing Readit project release
Date: 2018-01-20 02:00
Category: Tech
Tags: Python
Slug: announcing-readit-project-release
Authors: Ganesh Hubale

# Readit Tool v0.1 Release

Release day is always the best day for every developer! We’re excited to announce the release of v0.1 of the **Readit** tool. After a great development journey, it's time to share this with users. Today, we’ll walk you through the process of tagging and pre-releasing the project on GitHub, as well as releasing it on PyPI.

## GitHub Release Process

### 1. Tagging the Project
To prepare for a release, you first need to tag the final version of your branch. In our case, we tagged the `master` branch.

Here’s how to tag your project:
```bash
$ git tag -a tag_name -m "tag_message"
```

Next, push the tag to your remote repository:
```bash
$ git push origin tag_name
```

### 2. Creating a Pre-release
After pushing the tag, follow these steps:
- Go to the **Releases** section in GitHub.
- Click on **Tag** and add a release note with the features included in this version.
- Publish the notes to finalize the pre-release.
  
That’s it for the GitHub part. Now let’s move to releasing the project on PyPI.

## Releasing the Project on PyPI

We followed an excellent guide by Anwesha Das for publishing to PyPI. You’ll need to register with PyPI if you haven’t already.

### 1. Install Twine
First, install the `twine` tool:
```bash
$ sudo dnf install python3-twine
```

### 2. Create Source Distribution
Next, create a source distribution of the project:
```bash
$ python setup.py sdist
```
This will generate a tar file under the `dist` folder.

### 3. Upload to PyPI
Now, use `twine` to register and upload your project:
```bash
$ twine-3 register dist/readit-0.1.tar.gz
$ twine-3 upload dist/readit-0.1.tar.gz
```

### 4. Install Your Project
Once the project is uploaded, you can install it using:
```bash
$ pip3 install --user readit
```

Congratulations! You’ve successfully released your project on PyPI.

## Troubleshooting PyPI README Format
When we first visited the PyPI page for **Readit**, we noticed the README was displayed in raw text instead of a formatted view. After some research and reviewing projects like **diceware** and **gitcen**, we found that PyPI supports **ReStructuredText** (reST) for the long description.

To resolve this, we converted our `README.md` to reST format and updated our `setup.py` to use this as the long description.

## About the Readit Project

**Readit** is a powerful command-line bookmark manager that allows users to add, delete, update, and display bookmarks. You can find more information [here](https://github.com/pythonpune/readit).

This project has been in development for over a month and a half, and it’s been a great learning experience. I’d like to extend a big thank you to:
- @bhavin192, @akshay, @shitalmule, and @daivshala, my fellow project members.
- Mrs. S. Patil, our guide, for her constant motivation.
- Red Hat for providing us with this incredible opportunity.
  
Special thanks to my mentors from Red Hat:
- @chandankumar
- @amolkahat

Finally, a huge shoutout to the IRC members who helped us throughout the development process.

Thank you for supporting **Readit**!