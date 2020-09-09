# INFO4-PS

[Jonatha Anselmi](mailto:jonatha.anselmi@inria.fr) is in charge of the
lectures while [Arnaud Legrand](mailto:arnaud.legrand@imag.fr) is in
charge of practical sessions.

The pad is [here](http://pads.univ-grenoble-alpes.fr/p/INFO4_PS_20)
and the official schedule with room information is
[here](http://redirect.univ-grenoble-alpes.fr/ADE_ETUDIANTS_POLYTECH).


| Semaine    | Cours (Jeudi, 10h00-11h30)                      | TD (Vendredi, 9h45-13h00)                                                 |
|:-----------|:------------------------------------------------|:--------------------------------------------------------------------------|
| 7-11 sep.  | 14h00-15h00 [Introduction au cours](#10-09-2020-lecture-1) | (-> Lundi 14) [Introduction à Rstudio et Rmarkdown](#practical-session-1) |
| 14-18 sep. | [Probability basics](#lecture-2)                |                                                                           |
| 21-25 sep. | [TBA](#lecture-3)                               |                                                                           |
| 28-02 sep. | [TBA](#lecture-4)                               |                                                                           |
| 05-09 oct. | [TBA](#lecture-5)                               | [TBA](#practical-session-2)                                               |
| 12-16 oct. | [TBA](#lecture-6)                               | [TBA](#practical-session-3)                                               |
| 19-23 oct. | [TBA](#lecture-7)                               | [TBA](#practical-session-4)                                               |
| 26-3O oct. | Vacances                                        | Vacances                                                                  |
| 02-06 nov. | [TBA](#lecture-8)                               | [TBA](#practical-session-5)                                               |
| 09-13 nov. | [TBA](#lecture-9)                               | [TBA](#practical-session-6)                                               |
| 16-20 nov. | [TBA](#lecture-10)                              | [TBA](#practical-session-7)                                               |
| 23-27 nov. | [TBA](#lecture-11)                              | [TBA](#practical-session-8)                                               |
| 30-03 nov. | [TBA](#lecture-12)                              | [TBA](#practical-session-9)                                               |
| 07-11 dec. | [TBA](#lecture-13)                              | [TBA](#practical-session-10)                                              |
| 14-18 dec. |                                                 | [TBA](#practical-session-11)                                              |
| 21-25 dec. | Vacances                                        | Vacances                                                                  |
| 28-01 dec. | Vacances                                        | Vacances                                                                  |
| 04-09 jan. | Exam?                                           |                                                                           |

## [10-09-2020] Lecture 1
### Documents
- We will follow and cover most of the material presented in
  [Probabilités et statistique pour l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf),
  by Benjamin Jourdain.
- Slides
   + My slides
   + [Le hasard en informatique](http://www.lifl.fr/~jdelahay/pls/1998/051.pdf) by Delahay
- Additional references (deeper and longer explanations on most topics):
   + [Cours de Jean Bérard](http://math.univ-lyon1.fr/~jberard/cours-www.pdf)
   + Méthodes de simulation de variables continues: [Non-uniform
     Random Variate Generation](http://www.eirene.de/Devroye.pdf) by
     Luc Devroye
   + [Initiation aux
     probabilités](https://books.google.fr/books?id=6TjJW8tpQLwC&redir_esc=y&hl=fr)
     by Sheldon M. Ross.
   + Initiation aux Probabilités, by P. Brémaud (un ouvrage de référence, très très complet)
   + [Theoretical Computer Science Cheat Sheet](https://www.tug.org/texshowcase/cheat.pdf) :)

### Assignments
For next Monday (the practical session), you should

##### Answer our calculus survey
Take 10-20 minutes to answer this [Quick survey](pdf/Quick_0.pdf)
and send your answers (as an annotated pdf) to
`arnaud.legrand@imag.fr` with the following subject `[INFO4-PS] Quick
0 Nom, Prénom`. This should be done before Friday evening so
that we can analyze them before the next lecture. This survey will not
be graded, so no need to worry/cheat/whatever. The main objective is
(1) for us to identify those who need specific help in calculus (2)
for you to know whether you need to catch up some basics or not.

##### Install R and Rstudio
If you're running a debian or an ubuntu,
simply follow the following steps (otherwise, e.g., MacOS X or
Windows, you may want to have a look at [these
guidelines](https://gitlab.inria.fr/learninglab/mooc-rr/mooc-rr-ressources/-/blob/master/module2/ressources/rstudio_fr.org)):

``` shell
sudo apt-get install r-base r-cran-knitr r-cran-tidyverse
```
	
Installing software through your OS package manager is generally
the preferred way to do, although packages can also be installed
from R itself. Make sure you have a recent (>= 3.2.0) version or R. For example,
here is what I have on my machine:
	
``` shell	
R --version
```

    R version 3.5.2 (2018-12-20) -- "Eggshell Igloo"
    Copyright (C) 2018 The R Foundation for Statistical Computing
    Platform: x86_64-pc-linux-gnu (64-bit)

    R is free software and comes with ABSOLUTELY NO WARRANTY.
    You are welcome to redistribute it under the terms of the
    GNU General Public License versions 2 or 3.
    For more information about these matters see
    http://www.gnu.org/licenses/.

If it's not the case, it may be because you're running an old debian
stable or an old LTD ubuntu. In such case, you may want to [include
testing
packages](http://serverfault.com/questions/22414/how-can-i-run-debian-stable-but-install-some-packages-from-testing)... Ask
your local linux guru or run a VM if you're affraid to break your
OS. For the braves, let's keep going!

Rstudio and knitr are unfortunately not packaged within debian so
the easiest is to download the corresponding debian package on the
[Rstudio webpage](http://www.rstudio.com/ide/download/desktop)
and then to install it manually (depending on when you do this,
you should obviously change the version number and you may have to
update the url so that it matches your OS).

``` shell
cd /tmp/
wget https://download1.rstudio.org/desktop/bionic/amd64/rstudio-1.3.1073-amd64.deb
sudo dpkg -i rstudio-1.3.1073-amd64.deb
sudo apt-get update ; sudo apt-get -f install # to fix possibly missing dependencies
```

You may have trouble when installing some R packages. If so, try to
install these ones:

``` shell
sudo apt-get install libcurl4-openssl-dev libssl-dev
```

Finally you should be able to open rstudio. Try then to open a new
RMarkdown document (in the menu File New File R Markdown. When
doing so and depending on what has been installed on your machine,
Rstudio may complain that it requires upgraded versions of knitr,
rmarkdown and tinytex... :( Just proceed and you'll be ready for the
practical session.

## [14/10/2020] Practical Session 1
Today, we'll get familiar with R and Rstudio. I'll roughly cover this
[tutorial on
Rstudio](http://swcarpentry.github.io/r-novice-gapminder/01-rstudio-intro/index.html)
and this tutorial on [R
Markdown](https://swcarpentry.github.io/r-novice-gapminder/15-knitr-markdown/))
and show you how to use R to simulate and study simple stochastic
scenarios. 

TBD: Describe the scenario and various code we came up with.

## [17-09-2020] Lecture 2
### Documents
