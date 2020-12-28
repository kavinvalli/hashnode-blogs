## How to start a Django Project?

Django is one of the biggest web development with Python, web framework in the market and the biggest companies, including **Facebook, Google, etc**. have started using Django for it’s backend programming

So, here is how you can start your first Django Project

Prerequisites:
1. You should have basic knowledge about **Python** and should be well-versed with **Object Oriented programming in Python**

2. Basic frontend knowledge with **HTML, CSS** (You can use css frameworks like bootstrap to make your work easy)

3. That’s pretty much it… So let’s get started

If you have <span id="rmm"><span id="rmm"></span></span> come so far, in this blog, you must know Python well. So, since you have python installed, you would have got, PIP which is a python packaging tool, which is an equivalent of NPM if you have used JS

**So, first we need to create a directory. For that, go into the terminal and type:**


```
mkdir django_medium && cd django_medium
```


Once you have done that, you will be inside, the **django_medium** directory
Now, run:


```
pip3 install django
```


This would take some time. After that is done, you would have installed Django on your laptop.
However, it is always better to work on a **virtual environment**, so we will make one as follows


```
pip3 install virtualenv
virtualenv myenv --python=python3
```


This would:
1\. Install virtualenv on your device
2\. Create a vitualenv in the current directory, i.e. django_medium

Now, we need to activate this environment


```
source myenv/bin/activate
```


Now, that we have activated the environment, all our changes in here would not affect our device. So, now let us install django in this virtualenv


```
pip3 install django
```


Now, we will start a django project. To start a django project, run:


```
django-admin startproject django_medium .
```


**DON’T FORGET THE “.” IN THE END OF THE LINE**

Now, run:


```
python3 manage.py runserver
```


Now, go to the browser and type [http://127.0.0.1:8000](http://127.0.0.1:8000)
Voilà, you have successfully created your first django project