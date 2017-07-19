psycopg2 is a compiled module. That is why when you deploy it to AWS Lambda you probably get
an error like "_psycopg2.so file had incorrect ELF headers".

psycopg2/ and psycopg2-3.6/ are compiled versiones of lib psycopg2 for AWS Linux.
Just download it, put in into your vendored/ folder and import them like

here = os.path.dirname(os.path.realpath(__file__))
sys.path.append(os.path.join(here, "./vendored"))

Feel free to compile it yourself with a Docker like that https://serverlesscode.com/post/deploy-scikitlearn-on-lamba/.

Enjoy!
