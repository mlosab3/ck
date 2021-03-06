[![logo](https://github.com/ctuning/ck-guide-images/blob/master/logo-powered-by-ck.png)](http://cKnowledge.org)
[![logo](https://github.com/ctuning/ck-guide-images/blob/master/logo-validated-by-the-community-simple.png)](http://cTuning.org)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

Linux/MacOS: [![Build Status](https://travis-ci.org/ctuning/ck.svg?branch=master)](https://travis-ci.org/ctuning/ck)
Windows: [![Windows Build status](https://ci.appveyor.com/api/projects/status/iw2k4eajy54xrvqc?svg=true)](https://ci.appveyor.com/project/gfursin/ck)
Coverage: [![Coverage Status](https://coveralls.io/repos/github/ctuning/ck/badge.svg)](https://coveralls.io/github/ctuning/ck)

News
====
* Our CGO'07 paper (which later motivated creation of CK) received [CGO test of time award](http://dividiti.blogspot.fr/2017/02/we-received-test-of-time-award-for-our.html);
* CK-powered artifact received distinguished award at CGO'17 (Austin,TX): [paper with AE appendix and CK workflow](http://cTuning.org/ae/resources/paper-with-distinguished-ck-artifact-and-ae-appendix-cgo2017.pdf), [GitHub sources](https://github.com/SamAinsworth/reproduce-cgo2017-paper), [CK interactive dashboard snapshot](https://github.com/SamAinsworth/reproduce-cgo2017-paper/files/618737/ck-aarch64-dashboard.pdf);
* Our CK-related CNRS presentation "[Enabling open and reproducible research at computer systems conferences: the good, the bad and the ugly](http://dividiti.blogspot.fr/2017/03/enabling-open-and-reproducible-computer.html)"
* Michel Steuwer (University of Edinburgh) blogged about [CK concepts](https://michel-steuwer.github.io/About-CK);
* We [discussed with the commnunity](http://dividiti.blogspot.fr/2017/01/artifact-evaluation-discussion-session.html) how to use CK to improve Artifact Evaluation for CGO,PPoPP,PACT,RTSS,SC;
* Check out new [CK-AI](http://cKnowledge.org/ai) initiative to provide common JSON API and web-services for popular DNN frameworks (Caffe, TensorFlow, TensorRT) and prepare them for collaborative optimization (code and models);
* ARM uses CK as a front-end for systematic and reproducible benchmarking and tuning of real workloads: [GitHub](https://github.com/ctuning/ck-wa), [ARM TechCon'16 presentation](http://schedule.armtechcon.com/session/know-your-workloads-design-more-efficient-systems); 
* CK-powered open challenges in computer engineering have been updated: [link](https://github.com/ctuning/ck/wiki/Research-and-development-challenges);
* Fully updated documentation is now available: [Wiki](http://github.com/ctuning/ck/wiki), [Getting Started Guide](http://github.com/ctuning/ck/wiki/Getting-started-guide), [Portable workflows](http://github.com/ctuning/ck/wiki/Portable-workflows);
* We have moved Open Science resources [here](http://github.com/ctuning/ck/wiki/Enabling-Open-Science);
* We have added continuous integration for Linux and Windows;
* General Motors and dividiti crowdsource benchmarking and optimization of CAFFE (DNN framework) using CK: [GitHub](https://github.com/dividiti/ck-caffe), [Android app](https://play.google.com/store/apps/details?id=openscience.crowdsource.video.experiments);
* CK supports [Jupyter notebooks](http://jupyter.org) and [Docker](http://github.com/ctuning/ck-docker);
* cTuning foundation and ARM has received [HiPEAC technology transfer award](https://www.hipeac.net/research/technology-transfer-awards/2014) for the CK concept.

Introduction
============

Collective Knowledge is our "swiss knife" for open, collaborative and reproducible experimentation.
CK is a small, portable and customizable research platform to
* share artifacts as reusable and indexable Python components with unified JSON API and meta information (programs, benchmarks, data sets, tools, predictive models, etc) - see [Artifact Evaluation website](http://ctuning.org/ae/submission.html); 
* automate detection or installation of all software dependencies on Linux, Windows, MacOS, Android while enabling co-existence of different versions (compilers, benchmarks, libraries, tools) for a given experimental workflow across diverse Linux, Windows and Android based platforms via [CK cross-platform customizable package and environment manager](https://github.com/ctuning/ck/wiki/Portable-workflows);
* quickly prototype experimental workflows from shared components (such as customizable and multi-objective autotuning for DSL, OpenCL, CUDA, MPI, OpenMP and compiler flags) across diverse hardware and software ([CK repo](https://github.com/ctuning/ck-autotuning));
* crowdsource experiments across diverse hardware and workloads provided by volunteers and validate ideas or report unexpected behavior and bugs ([CK repo](https://github.com/ctuning/ck-crowdtuning));
* reuse and collaborative improve JSON description of all existing platforms from IoT to supercomputers ([CK repo](https://github.com/ctuning/ck-crowdtuning-platforms));
* abstract access to continuously evolving software and hardware stack ([CK repo](https://github.com/ctuning/ck-env));
* automate, reproduce and crowdsource empirical experiments using CK JSON-based web services ([live repo](http://cKnowledge.org/repo));
* unify access to predictive analytics (scikit-learn, R, DNN, etc) via unified JSON API and CK web services ([CK repo](https://github.com/ctuning/ck-analytics));
* enable reproducible and interactive articles ([CK repo](https://github.com/ctuning/ck-web)). 

Project homepage: 
* http://cKnowledge.org
* http://cTuning.org

Notable use cases:
* [Wikipedia article](https://en.wikipedia.org/wiki/Collective_Knowledge_(software)#Notable_usages)

CK concepts by Michel Steuwer:
* https://michel-steuwer.github.io/About-CK

License
=======
* Permissive 3-clause BSD license. (See `LICENSE.txt` for more details).

Minimal installation
====================

The minimal installation requires:

* Python 2.7 or 3.3+ (limitation is mainly due to unitests)
* Python PIP (if you would like to install CK via PIP)
* Git command line client.

On Ubuntu, you can install these dependencies via

```
$ apt-get install -y python python-pip git
```

On Windows, you can download and install these tools from the following sites:

* Git: https://git-for-windows.github.io
* Minimal Python: https://www.python.org/downloads/windows
* Anaconda scientific Python with all packages: https://www.continuum.io/downloads#_windows

You can now install stable CK version via PIP simply as following
(you may need to prefix it with "sudo" on Linux):

```
$ pip install ck
```

Alternatively, you can install development CK version in your local user space
via GIT as following:

```
 $ git clone https://github.com/ctuning/ck.git ck
```
and then add CK to PATH on Linux as following:
```
 $ export PATH=$PWD/ck/bin:$PATH
```
or on Windows as following:

```
 $ set PATH={CURRENT PATH}\ck\bin;%PATH%
```

Portable and customizable benchmarking
======================================

You can now test CK by pulling and executing one of many shared workflows.

For example, you can try the following community project to unify benchmarking
across ever changing hardware and software - just check that you have at least
one compiler installed for your target platform as described 
[here](https://github.com/ctuning/ck/wiki/Compiler-autotuning#Installing_compilers):

```
 $ ck pull repo:ck-autotuning
 $ ck pull repo:ctuning-programs
```

You can see shared programs in the CK format (JSON meta information 
describing how to compile and run shared program with all dependencies and data sets):
```
 $ ck list program
```

You can now compile a given program simply as following:
```
 $ ck compile program:cbench-automotive-susan --speed
```

Note, that CK will detect all available versions of required compilers (GCC, LLVM, ICC ...) 
and libraries on your system using [CK customizable cross-platform package and environment manager with JSON API and meta](https://github.com/ctuning/ck-env).
If some software dependencies are missing, CK will automatically install required packages
as described in this [article about portable CK workflows](https://github.com/ctuning/ck/wiki/Portable-workflows.mediawiki).

Now you can run your program simply as following:
```
 $ ck run program:cbench-automotive-susan
```

CK will ask you which command line to use and will automatically detect or install all required data sets.

If you have Android NDK/SDK installed on your host machine and Android device connected via ADB, 
you can simply compile and run the same problem on this device as following:
```
 $ ck compile program:cbench-automotive-susan --speed --target_os=android21-arm-v7a
 $ ck run program:cbench-automotive-susan --target_os=android21-arm-v7a
```

Artifact evaluation
===================

Collective Knowledge can help you convert your ad-hoc experimental scripts to portable, customizable and reusable 
with automatic cross-platform software installation and web-based experimental dashboards 
for [Artifact Evaluation](http://cTuning.org/ae) at the leading conferences and journals as briefly described
[here](https://github.com/ctuning/ck/wiki/Artifact-sharing). Feel free to ask for help from the CK community 
[here](http://groups.google.com/group/collective-knowledge)!

See example of a CGO'17 distinguished artifact from the University of Cambridge implemented using CK:
* [CK artifacts at GitHub](https://github.com/SamAinsworth/reproduce-cgo2017-paper)
* [Paper with AE appendix and CK workflow](http://ctuning.org/ae/resources/paper-with-distinguished-ck-artifact-and-ae-appendix-cgo2017.pdf)
* [PDF snapshot of the interactive CK dashboard](https://github.com/SamAinsworth/reproduce-cgo2017-paper/files/618737/ck-aarch64-dashboard.pdf)
* [CK concepts](https://michel-steuwer.github.io/About-CK)

Portable experiment crowdsourcing workflow
==========================================

You can check our shared workflow to crowdsource experiments across diverse
software and hardware provided by volunteers 
aka SETI@HOME for computer systems' research:


```
 $ ck pull repo:ck-crowdtuning
 $ ck crowdsource experiment
```

For example, you can execute shared workflow for collaborative program optimization
with all related artifacts, and start participating in multi-objective crowdtuning 
simply as following: 

```
 $ ck crowdtune program
```

You can also crowd-tune GCC on Windows as following:
```
 $ ck crowdtune program --gcc --target_os=mingw-64
```

If you have GCC or LLVM compilers installed, you can start continuously crowd-tune 
their optimization heuristics in a quiet mode (for example overnight) via

```
$ ck crowdtune program --llvm --quiet
$ ck crowdtune program --gcc --quiet
```

This experimental workflow will be optimizing different shared workloads
for multiple objectives (execution time, code size, energy, compilation time, etc)
using all exposed design and optimization knobs, while sending best performing 
optimizations to the public CK-based server:

* http://cTuning.org/crowd-results
* http://cknowledge.org/interactive-report

CK server will, in turn, perform on-line learning to classify optimization 
versus workloads which can be useful for compiler/hardware designers and 
performance engineers (described in more detail in http://arxiv.org/abs/1506.06256 ).

You can even participate in collaborative experiments using your Android mobile phone
by installing the following application from the Google Play Store:

* https://play.google.com/store/apps/details?id=openscience.crowdsource.experiments

If you want to try something more complex, you can check our cross-platform DNN unification,
customized installation and benchmarking via CK with JSON API and web services:
* http://cKnowledge.org/ai

You can find already shared artifacts and repositories here:
* List of shared repositories: https://github.com/ctuning/ck/wiki/Shared-repos
* List of shared modules: https://github.com/ctuning/ck/wiki/Shared-modules

Please check out CK getting started guides and CK wiki for further details:
* https://github.com/ctuning/ck/wiki/Getting-started-guide
* https://github.com/ctuning/ck/wiki/Portable-workflows
* https://github.com/ctuning/ck/wiki

You can also reuse and customize artifacts with CK-based experimental workflows 
shared at the leading computer systems' conferences:
* http://cTuning.org/ae/artifacts.html

Trying CK using Docker image
============================

If you would like to try CK without installing it, 
you can run the following Docker image:

```
 $ docker run -it ctuning/ck
```

However, the idea of CK is to be able to rebuild user experimental workflows
natively to take advantage of the latest software environment.

Also note that we added Docker automation to CK (to help 
evaluate artifacts at the conferences, share interactive 
and reproducible articles or crowdsource experiments for example). 

Please check 'ck-docker' repository at GitHub:

```
 $ ck show repo:ck-docker
```

You can download and view one of our CK-based interactive and reproducible articles as following:
```
 $ ck pull repo:ck-docker
 $ ck run docker:ck-interactive-article --browser (--sudo)
```

Testing CK
==========
You can test CK functionality via
```
 $ ck run test
```

Our related initiatives
=======================

* Artifact Evaluation for computer systems' conferences: http://cTuning.org/ae
* New publication model with the community-driven public reviewing: http://adapt-workshop.org

Plans
===================
* https://github.com/ctuning/ck/wiki/Plans

Motivation
==========
* https://github.com/ctuning/ck/wiki/Motivation

Authors
=======
* [Grigori Fursin](http://fursin.net/research.html), cTuning foundation / dividiti
* [Anton Lokhmotov](https://www.hipeac.net/~anton), dividiti

Questions/comments/discussions?
===============================
* Public wiki with open challenges in computer engineering:
  https://github.com/ctuning/ck/wiki/Research-and-development-challenges
* Mailing list for open, collaborative and reproducible R&D including knowledge preservation, sharing and reuse:
  http://groups.google.com/group/collective-knowledge
* Mailing list for software and hardware multi-objective (performance/energy/accuracy/size/reliability/cost)
  benchmarking, autotuning, crowdtuning and run-time adaptation: http://groups.google.com/group/ctuning-discussions

Publications
============

```
@inproceedings{ck-date16,
    title = {{Collective Knowledge}: towards {R\&D} sustainability},
    author = {Fursin, Grigori and Lokhmotov, Anton and Plowman, Ed},
    booktitle = {Proceedings of the Conference on Design, Automation and Test in Europe (DATE'16)},
    year = {2016},
    month = {March},
    url = {https://www.researchgate.net/publication/304010295_Collective_Knowledge_Towards_RD_Sustainability}
}
```

The concepts have been described in the following publications:

* http://tinyurl.com/zyupd5v (DATE'16)
* http://arxiv.org/abs/1506.06256 (CPC'15)
* http://hal.inria.fr/hal-01054763 (Journal of Scientific Programming'14)

* http://bit.ly/ck-multiprog16 (MULTIPROG'16)
* http://cknowledge.org/interactive-report
* http://arxiv.org/abs/1406.4020 (TRUST'14 @ PLDI'14)
* https://hal.inria.fr/inria-00436029 (GCC Summit'09)

If you found CK useful, feel free to reference 
any of the above publications. You can download 
all above references in one BibTex file 
[here](https://raw.githubusercontent.com/ctuning/ck-guide-images/master/collective-knowledge-refs.bib).

Testimonials and awards
=======================
* 2016: General Motors and dividiti use CK to crowdsource benchmarking and optimization of CAFFE: [public CK repo](https://github.com/dividiti/ck-caffe)
* 2015: ARM and the cTuning foundation use CK to accelerate computer engineering: [HiPEAC Info'45 page 17](https://www.hipeac.net/assets/public/publications/newsletter/hipeacinfo45.pdf), [ARM TechCon'16 presentation and demo](http://schedule.armtechcon.com/session/know-your-workloads-design-more-efficient-systems), [public CK repo](https://github.com/ctuning/ck-wa)
* 2014: HiPEAC technology transfer award: [HiPEAC TT winners](https://www.hipeac.net/research/technology-transfer-awards/2014)

Acknowledgments
===============

CK development is coordinated by the [cTuning foundation](http://cTuning.org) (non-profit research organization). 
We thank the [EU TETRACOM 609491 Coordination Action](http://tetracom.eu) for initial funding and
[dividiti](http://dividiti.com) for continuing support. We would also like to
thank Microsoft Research program for one-year grant to host the CK public
repository in the Azure cloud.  We are also extremely grateful to all
volunteers for their valuable feedback and contributions.
