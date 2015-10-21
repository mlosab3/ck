Collective Knowledge Infrastructure - enabling open,
collaborative and reproducible experimentation, 
knowledge sharing and predictive analytics.

Documentation, demo and video
=============================
* http://github.com/ctuning/ck/wiki
* http://cknowledge.org/repo
* https://youtu.be/Q94yWxXUMP0

License
=======
* Permissive 3-clause BSD license 
(see LICENSE.txt file for more details).

Requirements
============
* has been validated on Linux, Windows, Android (partially), Mac OS X
* only python >= 2.6 (3.0+ is natively supported)

Optional dependencies
=====================
* Python package 'Tkinter' or 'tkinter' or 'pyperclip' 
  if copy to clipboard functionality is required
* Python package 'matplotlib' to plot graphs
  (during autotuning or performance/energy/accuracy modeling)
* Python package 'psutil' to properly terminate running process 
  on Windows after timeout

Introduction
============

We have developed Collective Knowledge Framework and Repository (CK)
primarily to solve numerous problems we faced during past 20 years
of our research on building self-optimizing computer systems
(combining performance autotuning, machine learning and run-time adaptation):

* numerous and ever changing hardware
* black-box compilers
* ad-hoc tools and scripts with evolving and incompatible interfaces
* multiple heterogeneous and possibly proprietary data formats
* raising number of design and optimization choices
* raising amount of experimental data to process
* ad-hoc, outdated and non-representative benchmarks with limited data sets
* lack of unified and reproducible mechanisms for exchange of experimental results
* problems accessing proprietary software (compilers, benchmarks)
  and hardware for artifact evaluation

Eventually, we created CK as an open-source and light-weight SDK
(~200K python code) to help our colleagues preserve, organize,
describe, cross-link and share their code and data (benchmarks,
data sets, scripts, libraries, tools, experimental results,
models, tables, graphs, articles, etc) as reusable Python-based
components with a very simple API (just one function with
JSON in and JSON out) and JSON-based schema-free meta description, 
as shown in the following examples:
* https://github.com/ctuning/ctuning-programs 
* https://github.com/ctuning/ctuning-datasets-min
* https://github.com/ctuning/ck-analytics
* https://github.com/ctuning/ck-autotuning

CK also helps abstract access to ever-changing (and possibly
proprietary) tools and hardware via wrappers with the same JSON
API while protecting experimental setups from low-level
interface/data changes (wrappers handle such changes as well
as setting up environment for multiple versions of a given 
and possibly pre-installed tool or library). 

All components has DOI-style UID and can be transparently indexed 
and searched via third-party Hadoop-based ElasticSearch, 
shared via GIT, and connected together into experimental workflows
(CK pipelines) just as LEGO(TM) to quickly prototype various research ideas, 
crowdsource experiments, reproduce and improve past techniques.

Furthermore, CK can simplify connection of unified experiments 
to powerful predictive analytics tools such as scikit-learn 
and R (statistical analysis, data mining,  machine learning)
thus helping non-specialists perform statistical analysis of results,
automate  exploration of large, multi-dimensional design 
and optimization choices, speed up decision making, and
easily share results with colleagues via interactive graphs 
and articles, as demonstrated in our latest CK-powered interactive publications:
* http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:cd11e3a188574d80
* http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:6f40bc99c4f7df58

Unlike existing centralized web-based services 
that force users to upload all their code and data before
being processed, CK allows users organize their local artifacts 
and always keep track of them on their own machine 
while sharing them only if needed as P2P or via existing
private and public repositories. CK can be also easily
deployed by users in a cloud such as Amazon Web Service (AWS).

CK can also complement existing technology such as Docker 
and VM hardwired images by decomposing them into unified 
and reusable components with a simple, extensible and unified JSON API.
This is particularly useful for computer systems' R&D where 
software and even hardware is changing every day and becomes 
outdated very quickly. Hence, researchers would often like to 
be able  to actually rebuild, customize and rerun experimental 
setups using their own native tools (latest or different operating 
systems, compilers and libraries) rather than using VM images - 
CK was also developed to solve this issue. For example,
various research projects already use CK to share their
research artifacts and scenarios:
$ http://github.com/ctuning/reproduce-carp-project
$ http://github.com/ctuning/reproduce-pamela-project
$ http://github.com/ctuning/reproduce-clsmith
$ http://github.com/ctuning/reproduce-ck-paper 

CK can be invoked in a unified way via command line or JSON web service.
It can also be directly invoked from other programs and tools
written in practically any language including C, C++, Fortran,
PHP and Java using OpenME event-based plugin framework (we worked
with the community to add similar plugin interface to GCC 4.6+
and plan to add it to LLVM).

We hope that our approach will let industry, academia and
volunteers work together to gradually improve research
techniques and continuously share realistic benchmarks and data
sets. We believe that this can eventually enable truly open,
collaborative, interdisciplinary and reproducible research
to some extent similar to physics, other natural sciences,
Wikipedia and open-source movement. It may also help computer
engineers and researchers become data scientists and focus
on innovation while liberating them from ad-hoc, repetitive,
boring and time consuming tasks. It should also help solve some
of big data problems we faced since 1993 by preserving
predictive models (knowledge) and finding missing features
rather than keeping large and possible useless amounts of raw
data.

You may check out our motivation as well as real usage scenarios,
 CK-powered interactive papers and websites (some are based on previous 
version aka Collective Mind) here:

* [Interactive article 1] http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:6f40bc99c4f7df58
* [Interactive article 2] http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:cd11e3a188574d80
* [All shared artifacts via CK]: http://github.com/ctuning/reproduce-ck-paper
* [Our open publication model] http://arxiv.org/abs/1406.4020
* [Live CK repository] http://cknowledge.org/repo
* [CK-generated interactive CV] http://fursin.net/cv.html
* [ADAPT workshop with Reddit-based reviewing] http://adapt-workshop.org
* [Android client for crowd-benchmarking] https://play.google.com/store/apps/details?id=com.collective_mind.node

Further details about CK including getting started guide, 
real usage scenarios, and developer guide is available here:

* https://github.com/ctuning/ck/wiki

Copyright
=========
This software is being developed by the non-profit 
cTuning foundation and its volunteers.

(C)opyright 2014-2015 Grigori Fursin, 
cTuning foundation and contributors

http://cTuning.org

See COPYRIGHT.txt for more details.

Authors
=======
* Grigori Fursin, http://fursin.net
* Anton Lokhmotov, https://www.hipeac.net/~anton

Installation
============
We made a special effort to make CK installation 
as simple as possible - it requires only standard 
Python version 2.6 or above (3.x is supported). 

CK has been successfully tested by volunteers on various 
platforms including Ubuntu, OpenSUSE, CentOS, MacOS X, 
Android (partial support through web services and OpenME) 
and most of the recent Windows versions. 

Note: since user packages may require extra functionality
such as scipy and scikit-learn, we have been 
successfully using Anaconda python distribution
which includes all scientific packages required 
for predictive analytics in CK.

## Root installation
Root installation will automatically add ck script 
to your PATH and will also install CK as standard
python module.

You can install CK either via GIT (latest, 
self-updatable, development version) or via PIP
(please, remove 'sudo' on Windows).

### PIP installation

Official stable release via PyPi archive:

 $ sudo pip install ck

Latest development version from GitHub:

 $ sudo pip install https://github.com/ctuning/ck/archive/master.zip

### Anaconda installation

Official stable release:

 $ conda install -c http://conda.anaconda.org/ctuning ck

### Git installation (latest from GitHub)

 $ git clone https://github.com/ctuning/ck.git ck

 $ cd ck

 $ sudo python setup.py install

## Non-root installation
Non-root installation will just require you to add
path to bin/ck to your PATH environment variable.

### PIP installation

Official stable release via PyPi archive:

 $ pip install --user ck

Latest development version from GitHub:

 $ pip install --user https://github.com/ctuning/ck/archive/master.zip

On Linux, it will most likely install ck script in
".local/bin" so you should add it to your PATH, i.e.

 $ export PATH=$HOME/.local/bin:$PATH

On Windows, it will most likely install ck script
in "C:\Users\{YOUR LOGIN}\AppData\Roaming\Python\Scripts
that you should add to PATH environment variable.

### Git installation (latest from GitHub)

 $ git clone https://github.com/ctuning/ck.git ck

 $ cd ck

 $ export PATH=$PWD/bin:$PATH

Usage
=====

You can check that CK is installed correctly via:

 $ ck

You should see information about ck options.

If you have IPython installed, you can then check CK installation
as following:

 $ ipython

 $ import ck.kernel as ck

 $ ck.test()

 $ ck.access('list module')

 $ ck.access('load kernel default')

Now, you can use CK to pull various public CK repositories
(code and data shared as reusable components via GitHub
or Bitbucket) and run shared experimental workflows
(for example, to crowd-benchmark and autotune programs,
build predictive models of performance, analyze representative
benchmarks and data sets, install missing tools, ...).

For example, compiling and running any shared benchmark 
on your Linux machine with GCC can be done simply as:

 $ ck pull repo:ctuning-programs

 $ ck compile program:cbench-automotive-susan --speed

 $ ck run program:cbench-automotive-susan

You will be asked a few questions and for now you can just press Enter 
to select the default choices.

Compiling and running such benchmarks on Windows or Android,
autotuning or crowdtuning them (performance, energy, accuracy, size, etc),
adding more data sets, applying machine learning to predict optimizations,
and any other shared scenario requires a few more steps 
as described in our "Getting Started Guide":

* https://github.com/ctuning/ck/wiki

Adding new CK modules as containers for own data, as a wrapper
for some tool or as a workflow is also straightforward. 
For example, you can add your own module 'hello' with an action 'say'
and with an entry 'world' as following (you can select all
default values by just pressing Enter):

 $ ck add module:hello

 $ ck add_action module --func=say

 $ ck add hello:world

 $ ck say hello:world

You can now find and customize Python dummy function 'say' 
in the CK module 'hello' (module.py) via
 
 $ ck find module:hello

You can also find associated CK entry hello:say and modify 
its meta information (.cm/meta.json) via

 $ ck find hello:world

Please, follow CK guide for more details:

* https://github.com/ctuning/ck/wiki

Questions/comments/discussions?
===============================
Please, use our mailing lists:
* General topics of knowledge preservation, sharing and reuse
  as well as collaborative and reproducible R&D: http://groups.google.com/group/collective-knowledge
* Software and hardware performance/energy/size/reliability
  (auto/crowd)tuning: http://groups.google.com/group/ctuning-discussions

Publications
============
Concepts has been described in the following publications:

* http://arxiv.org/abs/1506.06256
* http://hal.inria.fr/hal-01054763
* http://arxiv.org/abs/1406.4020
* https://hal.inria.fr/inria-00436029

If you found CK useful and/or interesting, you are welcome
to reference any of the above publications in your articles
and reports.

Fun
===
* CK GIT commits as a video: http://cknowledge.org/soft/commits/ck-visualization.mp4

CK-powered projects
===================

CK is currently used in the following projects:

* building public repository of benchmarks, data sets, tools, predictive
models and optimization knowledge in a unified format with the help
of the computer engineering community
(http://cknowledge.org/repo , http://c-mind.org/repo)

* implementing universal multi-dimensional, multi-objective,
plugin-based autotuning combined with crowdsourcing, predictive
analytics and run-time adaptation (to enable self-optimizing
computer systems). We support OpenCL, CUDA, OpenMP, MPI, compiler
and any other tuning for performance, energy, size, reliability,
cost and any other metrics across small kernels/codelets and
large applications (http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:cd11e3a188574d80).

* implementing crowd-benchmarking (crowdsourcing workload characterization
and compiler heuristic construction across numerous architectures using shared
computational resources such as mobile phones, tablets, cloud services, etc.
(https://play.google.com/store/apps/details?id=com.collective_mind.node ,
http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:cd11e3a188574d80)

* supporting artifact evaluation initiatives for major conferences
and journals where all artifacts are shared as reusable components (and not
just as black box virtual machine images) along with publications
(http://ctuning.org/event/ae-ppopp2016 , http://arxiv.org/abs/1406.4020 ,
http://adapt-workshop.org)

* enabling open, collaborative and reproducible research and experimentation
with interactive publications focusing on computer engineering
( http://cTuning.org/reproducibility-wiki )

* enabling interactive and reproducible articles for Digital Libraries
(http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:cd11e3a188574d80 ,
http://cknowledge.org/repo/web.php?wcid=29db2248aba45e59:6f40bc99c4f7df58)

* serving as a personal knowledge manager to organize, interconnect
and preserve all personal coda and data via simple JSON
meta with UIDs and semantic tags.

You are welcome to add your own CK-powered project here!

Acknowledgments
===============

CK development is coordinated by the non-profit cTuning foundation
(cTuning.org). We would like to thank the EU TETRACOM 609491 project
(www.tetracom.eu) for initial funding and dividiti (www.dividiti.com)
for continuing support. We are also extremely grateful to all volunteers
for their valuable feedback and contributions.
