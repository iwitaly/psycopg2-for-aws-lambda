[psycopg2](http://initd.org/psycopg/) is a compiled Python's driver for SQL. That is why when you deploy it to AWS Lambda you probably get
an error
> _psycopg2.so file had incorrect ELF headers
or
> No module named _psycopg

Check [Stack](https://stackoverflow.com/questions/36607952/using-psycopg2-with-lambda-to-update-redshift-python) for more about this.

---

`psycopg2/` and `psycopg2-3.6/` are already compiled versiones of lib `psycopg2` for AWS Linux.
Just download it, put in into your vendored/ folder and import them like

```
here = os.path.dirname(os.path.realpath(__file__))
sys.path.append(os.path.join(here, "./vendored"))
```

Feel free to compile it yourself with a Docker with [this tutorial](https://serverlesscode.com/post/deploy-scikitlearn-on-lamba/).

Enjoy!
