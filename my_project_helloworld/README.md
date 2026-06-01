Commit : 1



Download uv package manager:
============================

uv is a modern Python package manager and environment management tool

Installed like bwlow:
=======================

PS D:\Aziro_AI_traning\Working_folder\langchain-course> pip install uv
WARNING: Cache entry deserialization failed, entry ignored
Collecting uv
  Downloading uv-0.11.17-py3-none-win_amd64.whl.metadata (12 kB)
Downloading uv-0.11.17-py3-none-win_amd64.whl (25.1 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 25.1/25.1 MB 11.3 MB/s  0:00:02
Installing collected packages: uv
Successfully installed uv-0.11.17
PS D:\Aziro_AI_traning\Working_folder\langchain-course>

creating / intiating a project:
================================

PS D:\Aziro_AI_traning\Working_folder\langchain-course> uv init my_project_helloworld
Initialized project `my-project-helloworld` at `D:\Aziro_AI_traning\Working_folder\langchain-course\my_project_helloworld`
PS D:\Aziro_AI_traning\Working_folder\langchain-course>

uv init <project_name> commmand:
---------------------------------

When we do this command uv init <project_name>

Below project folder structure gets created:

my_project_helloworld
	| 
	|----- .python-version
	|----- main.py
	|----- pyproject.toml
	|----- README.md
	
	
.python-version - Contains the Python version for the project.

main.py -> Starter Python file.

pyproject.toml (Most Important File) -> This is the modern Python project configuration file.

README.md  -> Project documentation file.


here .toml appreviates Tom's Obvious Minimal Language 

It is a configuration file format.

uv add command:
----------------

The uv add command is used to install a package and automatically register it as a dependency in your project configuration.


	
uv documntation:
----------------

https://docs.astral.sh/uv/

install the langchain-openai package to your project's pyproject.toml
----------------------------------------------------------------------

uv add langchain-openai

PS D:\Aziro_AI_traning\Working_folder\langchain-course\my_project_helloworld> uv add langchain-openai    
Using CPython 3.14.5 interpreter at: C:\Users\mgopi\AppData\Local\Programs\Python\Python314\python.exe
Creating virtual environment at: .venv
Resolved 38 packages in 1.86s
Prepared 37 packages in 5.50s
░░░░░░░░░░░░░░░░░░░░ [0/37] Installing wheels...                                                                                            warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
Installed 37 packages in 5.94s
 + annotated-types==0.7.0
 + anyio==4.13.0
 + certifi==2026.5.20
 + charset-normalizer==3.4.7
 + colorama==0.4.6
 + distro==1.9.0
 + h11==0.16.0
 + httpcore==1.0.9
 + httpx==0.28.1
 + idna==3.17
 + jiter==0.15.0
 + jsonpatch==1.33
 + jsonpointer==3.1.1
 + langchain-core==1.4.0
 + langchain-openai==1.2.2
 + langchain-protocol==0.0.16
 + langsmith==0.8.8
 + openai==2.38.0
 + orjson==3.11.9
 + packaging==26.2
 + pydantic==2.13.4
 + pydantic-core==2.46.4
 + pyyaml==6.0.3
 + regex==2026.5.9
 + requests==2.34.2
 + requests-toolbelt==1.0.0
 + sniffio==1.3.1
 + tenacity==9.1.4
 + tiktoken==0.13.0
 + tqdm==4.67.3
 + typing-extensions==4.15.0
 + typing-inspection==0.4.2
 + urllib3==2.7.0
 + uuid-utils==0.16.0
 + websockets==16.0
 + xxhash==3.7.0
 + zstandard==0.25.0
PS D:\Aziro_AI_traning\Working_folder\langchain-course\my_project_helloworld> 



next command : uv add python-dotenv
-----------------------------------

This command:

Installs the python-dotenv package in your project's virtual environment.
Adds it as a dependency in pyproject.toml.
Updates the lock file (uv.lock).

PS D:\Aziro_AI_traning\Working_folder\langchain-course\my_project_helloworld> uv add python-dotenv
Resolved 39 packages in 719ms
Prepared 1 package in 295ms
░░░░░░░░░░░░░░░░░░░░ [0/1] Installing wheels...                                                                                             warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
Installed 1 package in 444ms
 + python-dotenv==1.2.2
PS D:\Aziro_AI_traning\Working_folder\langchain-course\my_project_helloworld>


next :  uv add --dev black isort
----------------------------------

Why --dev?

black and isort are development tools, not runtime dependencies. Using --dev adds them to the development dependency group in pyproject.toml.

before .toml file
------------------

[project]
name = "my-project-helloworld"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.14"
dependencies = [
    "langchain-openai>=1.2.2",
    "python-dotenv>=1.2.2",
]


After installtion:
-------------------

[project]
name = "my-project-helloworld"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.14"
dependencies = [
    "langchain-openai>=1.2.2",
    "python-dotenv>=1.2.2",
]

[dependency-groups]
dev = [
    "black>=26.5.1",
    "isort>=8.0.1",
]

next:
------

created a .gitignore file and pasted the standard template:

https://github.com/github/gitignore/blob/main/Python.gitignore



next:
------

create a .env file

THEN add the OPENAI_API_KEY = 

(do not commit api key on github)

go to openai -> create ccount-> generate api keey

https://platform.openai.com/welcome?step=try

my first api key: xyz

