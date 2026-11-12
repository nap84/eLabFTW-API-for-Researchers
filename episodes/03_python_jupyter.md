---
title: "Using the API with Python in Jupyter Notebooks"
teaching: 40 # teaching time in minutes
exercises: 30 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- What is Python?
- What is basic Python syntax?
- What is a Jupyter Notebook?
- Where can I find Python examples for the eLabFTW API?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Write basic Python code
- Install the eLabFTW Python package
- Write and execute basic markdown and Python in Jupyter Notebooks
- Find and reuse eLabFTW Python examples for API clients

::::::::::::::::::::::::::::::::::::::::::::::::

## What is Python?

Python is a high‑level, interpreted programming language that was created in the early 1990s by Guido van Rossum. It reads almost like plain English, which makes it especially attractive for people whose primary expertise is not computer science (e.g. biologists, chemists, physicists, engineers).  

When you run a Python script, the Python interpreter reads the source code line‑by‑line, translates it into byte‑code, and executes it on the fly – you do not need a separate compilation step.

- Python gives you a clean, readable language that lets you focus on the scientific question rather than low‑level programming details.  
- Its extensive libraries let you go from raw data to publication‑quality figures in a few lines of code.  
- When performance becomes critical, you can combine Python with compiled extensions or off‑load heavy work to specialized tools.

## What is a Jupyter Notebook

Let's open a new Jupyter Notebook called `ep_3_python_jupyter.ipynb`. In Jupyter Lab, you can do this by clicking the blue `+` button, and then clicking the Python tile under notebook. Right-click the newly created notebook to and select rename to rename it.

::::::::::::::::::::::::::::::::: instructor

Use the opened notebook to show the points below.

::::::::::::::::::::::::::::::::::::::::::::::::

A Jupyter Notebook is an interactive web‑based document that combines executable code, rich text, plots, and multimedia in a single, linear layout. You open it in a browser, but the Python (or other language) kernel runs on your computer (or on a remote server) and evaluates each cell on demand.
Core concepts

- **Cells** – The notebook is divided into blocks called cells.  

  - **Code cells** contain Python (or R, Julia, …) statements that are sent to the kernel when you press **Shift + Enter**. The output—text, tables, images, interactive widgets—appears directly below the cell.  
  - **Markdown cells** hold formatted text written in **Markdown** (headings, lists, links, LaTeX equations, etc.). They let you annotate your analysis, describe the rationale, or document results.

- **Kernel** – A background process that executes the code. The notebook UI sends the cell’s source to the kernel, receives the result, and displays it. You can restart, interrupt, or switch kernels (e.g., Python 3, R) without leaving the notebook.

- **Output** – Anything that a normal read–eval–print loop (REPL) would print can appear: plain text, JSON, tables, Matplotlib/Plotly figures, HTML, LaTeX‑rendered equations, or interactive widgets (sliders, drop‑downs).

## Crash course: Python Basics

### 1. Printing & basic data types  

:::::::::::::::::::::::::::::::::::::: instructor

These will be live coded in a Jupyter notebook.

::::::::::::::::::::::::::::::::::::::::::::::::


```python
# Print a greeting
print("Hello, eLabFTW researcher!")

# Numbers, strings, booleans, which can be stored in variables
my_int   = 42            # integer
my_float = 3.14          # floating‑point
my_bool  = True          # boolean

print(my_int, my_float, my_bool)
```

**Expected output**  

```
Hello, eLabFTW researcher!
42 3.14 True
```

### 2. Variables & dynamic typing  

```python
a = 10          # a is an int
a = a * 2.5    # now a becomes a float (25.0)

print(a)
```

**Output**  

```
25.0
```

### 3. Lists (ordered collections)  

We can define lists of objects. They can be any type of data. For example strings (but they could also be mixed type). 

We can use indexing to retrieve items (starts at 0!), slice lists, and append new items.

```python
samples = ["S1", "S2", "S3"]   # create a list
print(samples[0])              # first element → "S1"
print(sample[2:3])             # slice, print part of list according to index

# Append a new sample name
samples.append("S4")
print(samples)
```

**Output**  

```
S1
['S1', 'S2', 'S3', 'S4']
```

### 4. Loop over a list (for‑loop) to create a dictionary

We can iterate over a series, such as a list, to perform operations on each item. In this case, we have another data type, a dictionary, which is a collection of key:value pairs. We have a pattern where we:

1. Initialize an empty dictionary, which is done with curly braces.
2. Iterate over the sample list.
3. Assign the key (sample) in the dictionary a value (the length pf the sample name string).

```python
results = {}
for sample in samples:
    results[sample] = len(sample)   # store the length of the name

print(results)
```

**Output**  

```
{'S1': 2, 'S2': 2, 'S3': 2, 'S4': 2}
```

### 5. Conditional statements  

Conditional statements give you the option to check a condition. In `if`-statements, if this condition is true, the indented code block will be varied out. An `else`-statement can be used in combination with an `if` to provide instructions on what to do if the `if` fails.

```python
threshold = 5
value = 7

if value > threshold:
    print("value is larger")
else:
    print("value is smaller or equal")
```

**Output**  

```
value is larger
```

### 6. Defining and calling a function  

Functions serve as reusable pieces of code. We define them using `def`:

```python
def check_value(value, threshold):
  if value > threshold:
    return "value is larger" 
  else:
    return "value is smaller or equal"
```

Then we can call them using their name and passing any required parameters in parentheses:

```
result = (check_value(7, 5))
print(result)
```

**Output**

```
'value is larger'
```

#### Built-in Functions

There are a number of built-in functions in Python, which means we don't have to define everything ourselves. We've already seen some of these, for example, the `print()` function. Again, we call the function by it's name and pass what it needs in the parentheses (as above `print("Hello, eLabFTW researcher!")`).

The built-in function `help()` allows us to retrieve the documentation on functions, including built-in ones. For example, we can call `help()` on the built-in function `type()`:

```python
help(print)
```

**Output**

```
Help on built-in function print in module builtins:

print(*args, sep=' ', end='\n', file=None, flush=False)
    Prints the values to a stream, or to sys.stdout by default.
    
    sep
      string inserted between values, default a space.
    end
      string appended after the last value, default a newline.
    file
      a file-like object (stream); defaults to the current sys.stdout.
    flush
      whether to forcibly flush the stream.
``` 

Another useful built-in function is `len()` which gives is the length of things, such as, strings, lists, or dictionaries:

```python
len('Hello')
```

**Output**
```
5
```

```python
samples = ["S1", "S2", "S3"]   # create a list
len(sample)
```

**Output**

```
3
```

See the [Python Docs on built-in functions](https://docs.python.org/3/builtins/functions.html).

Please note, we are working in a Jupyter Notebook and running text snippets. This is a great way to learn and explore data. If you were running automated scripts, you would write these in Python files, e.g., `my_script.py` which can be run in the terminal

```bash
python my_script.py
```

::::::::::::::::::::::::::::::::::::::::::: challenge
What will be printed?

```python
def add_five(value):
  return value + 5

result = add_five(5)
next_value = result + 1
print(result)
```

A. 11
B. 10  
C. TypeError  

::::::::::::::::::::::::::::::::::::::: solution

**B** – The function adds 5 to the passed value of 5, returning the value of 10. This returned valued is stored in `result` and doesn't change afterwards.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## The eLabFTW Python API Library

One of the advantages of Python is that there are many ready-made libraries that allow us to easily reuse code others have created for a specific purpose.

For eLabFTW, there is **elabapi-python**. We can find information on it via the [API docs selection page](https://doc.elabftw.net/api/) by clicking `Python Library (v2)`.

Here, we can find some examples and information such as installation. We will do something similar to what the page says and install it directly via our Jupyter Notebook:

```bash
%pip install elabapi-python
```

::::::::::::::::::::::::::::::::::::: callout

This installs it directly in the environment we are working in so it is accessible to our notebook.

To install it locally (e.g., if you are working outside of the Jupyter environment), open a terminal window and install via pip. This usually looks like:

```bash
pip install elabapi-python
```

However, your Python and pip installation may use `pip3` instead of `pip`.

As indicated by the [elabapi-python installation instructions](https://github.com/elabftw/elabapi-python#installation), it is highly recommended to work in a virtual environment. We recommend [`uv`](https://docs.astral.sh/uv/) for creating and managing these:

```bash
cd workshop_data # change directory folder (if not already in this folder)
uv init --bare # initialize the project in the desired directory
uv add elabapi-python python-dotenv # add the API client and .env support
uv sync
```

The package `elabapi-python` is imported as `elabapi_python`, and
`python-dotenv` is imported as `dotenv` in `client.py` (we will get to that script in a minute). Ensure you have added your credentials and the URL to a `.env` (or `secrets.env`) file.

::::::::::::::::::::::::::::::::::::::::::::::::

Once downloaded, we need to import the library into our notebook or scripts:

```python
import elabapi_python
```

Python does not allow dashes, therefore, this is replaced with an underscore when calling the library.

To get basic help on any Python library in Jupyter, we can use the `help()` function. For example, to get help on the `elabapi_python` library, we can run:

```python
help(elabapi_python)
```

Honestly, for this specific case, the help output is not extremely helpful. However, it does give us some information on the library. We can also use the `dir()` function to get a list of all the functions in the library:

```python
dir(elabapi_python)
```

If we start the [API docs](https://doc.elabftw.net/api/) again and click on `Python Library (v2)`, we get are taking to a GitHub repository.

Here, we have the [examples folder](https://github.com/elabftw/elabapi-python/tree/master/examples) on Github. This contains a nifty [client configuration file](https://github.com/elabftw/elabapi-python/blob/master/examples/client.py). This has already been downloaded and included in your `workshop_data` directory. We have made some small adjustments to ensure the secrets load correctly.

In the Python library, there are various clients that can be used to interact with the eLabFTW API. First, you set up the main one, which has already been done in `client.py`, then, you can create the others.

We import the main api client into our notebook using:

```python
from scripts.client import api_client
```

Note: ensure your are in the correct directory, `workshop_data/`.

:::::::::::::::::::::::::::::::::::::::::::::::::: callout

When writing, you can avoid a lot of spelling errors by using <kbd>tab</kbd> to get suggestions.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::

You may get an error here for missing packages, especially dotenv:

```python
%pip install python-dotenv
```

Let's look at a couple examples in the GitHub repo.

Check out [00_getting-started.py](https://github.com/elabftw/elabapi-python/blob/master/examples/00-getting-started.py). We can see an info client:

```python
info_client = elabapi_python.InfoApi(api_client)
api_response = info_client.get_info()
api_response
```

:::::::::::::::::::::::::::::::::::::::::::::::::::: callout

In Jupyter Notebooks, we often get a pretty printed output without using a `print()` statement. This only works for the last line of a cell, so if you want to see the output of multiple lines or when using in a script, you will need to use `print()`.

For example:

```python
api_response
4
```

will output the number 4.

As opposed to:

```python
print(api_response)
4
```

which will output both `api_response` and the number 4.
::::::::::::::::::::::::::::::::::::::::::::::::::::

Back to the clients. We kind of see the pattern. We create a client for the methods we see in the [HTML API Docs](https://doc.elabftw.net/api/elabapi-html/), and then use the method. We can do the exact same thing we did before and get our own user info:

```python
users_client = elabapi_python.UsersApi(api_client)
me = users_client.read_user('me') # alternative would be to use an ID
me
```

Similarly, we can see an experiment client in the examples:

```python
exp_client = elabapi_python.ExperimentsApi(api_client)
```

Check out [line 87](https://github.com/elabftw/elabapi-python/blob/master/examples/00-getting-started.py#L87), which shows us how we retrieve an experiment. Remember how we created and retrieved an experiment in the terminal using cURL? Let's try the same thing here using the experiment ID from the last lesson.

```python
exp_id = 94 # example; replace with your experiment ID
exp = exp_client.get_experiment(exp_id)
print(exp)
```

You can see, this does the same things as we were doing before, but many of us find Python easier to read and understand than the terminal commands. This is especially true when we start to combine multiple steps into a single script.

::::::::::::::::::::::::::::::::::::: challenge

What is the code for the client that interacts with resources in eLabFTW? Create this client in your notebook and use it to:

1. Retrieve all resources (you have access to) from your eLabFTW instance.
2. Retrieve the bluetooth thermometer resource (from the last episode).

Hint: Look through the [examples](https://github.com/elabftw/elabapi-python/tree/master/examples) and keep your eyes out for a different word than _resources_. We saw this in [episode 01](01_API), as well.

:::::::::::::::::::::::: solution

An example can be found in [05-create-modify-item](https://github.com/elabftw/elabapi-python/blob/master/examples/05-create-modify-item.py) in line 6:

```python
itemsApi = elabapi_python.ItemsApi(api_client)
```

To retrieve and view all resources you have access to (1):

```python
resources = itemsApi.read_items()
resources # outputs the resource to the jupyter notebook
```

To retrieve a specific resource (2):

```python
resource = itemsApi.get_item(144)
resource # outputs the resource to the jupyter notebook
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Jupyter Notebooks combine executable Python code, Markdown, and output
- Python variables, collections, loops, conditionals, functions, and JSON support basic data workflows
- The `elabapi-python` package provides Python clients for the eLabFTW API
- A configured API client can be reused to access information, experiments, and resources
- API documentation and examples help identify the appropriate client and method

:::::::::::::::::::::::::::::::::::::::::::::::
