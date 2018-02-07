Title: flake8 and autopep8
Date: 2018-01-20 02:00
Category: Testing
Tags: general
Slug: what-are-flake8-and-autopep8
Authors: Ganesh Hubale
Summary:

flake8 and autopep8 are magical things, I have ever seen in my open source journey till now. Open Source stuff is so interesting, if you want to work in it. Butthere is one condition, you must understand these things deeply and it requires patience or good mentor like google. I have attended my conversation with my mentor and some colleagues on IRC. I had query about failing my travis-ci builds again and again. But it has other reasons like I didn't written test cases but mentioned `script: pytest` in `travise.yml` file. They told me to go for only pep8 standards testing and to do this, I have to add `flake8` to the `travis.yml` file. My first reaction was like what are they talking about, I didn't even listen about flake8. How could I deal with it?
Friends, Finally I understood `fake8` thoroughly and used too in my project. `autopep8` is python package which helps to format code. These two are independent.

> `flak8` helps to find errors in python code formating and `autopep8` helps us to fix these errors.

Now we will go for it's installations and use:

# flake8

- installation
```
pip install flake8
```
- use
```
flake8 example.py
```
- help
```
flake8 --help
```

# autopep8
- installation
```
pip install --upgrade autopep8
```
- use
```
autopep8 --aggressive example.py
```
- help
```
autopep8 --help
```

Thank you,
