---
layout: post
title: Installing Transrate
date: "2013-10-19 12:53"
comments: true
categories: bioinformatics
published: true
---

{% include JB/setup %}

# Installing Transrate

[Transrate](https://github.com/Blahah/transrate) is a program for analysing the quality of transcriptome assemblies. It's designed for anyone who is doing de-novo assembly of transcriptomes from RNA-Seq data. Recently I've had several requests for help installing transrate from non-expert users. This set of instructions is aimed at helping users new to the linux/unix environment to get up and running.

Transrate is written in the Ruby programming language. This makes it fairly easy to install. It also depends on some external software, which can be more complicated for new users to install. Here we'll go through the whole process step-by-step.

<!-- more -->

## Installing Ruby

The easiest way to get Ruby installed is to use the RVM (Ruby Version Manager).

First, open up your Terminal app. Then, paste in the commands below and hit enter.

**Note: commands in boxes like the one below can be copy-pasted into the terminal to run them. Lines starting with a # are comments, and will do nothing when run.**

{% highlight bash %}
# download and run the RVM installation code
\curl -L https://get.rvm.io | bash -s stable --ruby
{% endhighlight %}

That was easy!

## Installing Transrate

Programs written in ruby can be packaged up in an easy-to-install bundle called a *gem*. There's a great website, [RubyGems](http://rubygems.org), that lists the available gems. To install a gem, you just run:

{% highlight bash %}
gem install gemname
{% endhighlight %}

Transrate is a gem, so to install it we run:

{% highlight bash %}
gem install transrate
{% endhighlight %}

This will install transrate itself along with all the other ruby gems it depends on.

## External dependencies

Three programs, USEARCH, Bowtie 2 and eXpress, are required by transrate.

In order to install them, you need to put the executable program files in a directory on your computer, and then tell the computer where to find them. You do this by adding the location of the files to your PATH. PATH is an [environment variable]() that simply lists the places you have progams installed. When you run the Terminal, it loads the PATH and then any time you run a command, it searches all the directories listed in the PATH for the program whose name you have typed.

### Creating an installation directory

It's useful to have one place where you install new programs. That way, you only have to add one directory to the PATH, and you always know where to put new things.

Let's create an `~/apps` directory where we can download program files, and an `~/apps.bin` directory where we'll put links to the executables.

{% highlight bash %}
mkdir ~/apps
cd ~/apps
mkdir bin
{% endhighlight %}

Now let's tell the command line where to find our new directory. We do this by making a command to add the location to the path, and then putting that command in a file that gets run each time the terminal opens:

{% highlight bash %}
echo "export PATH=$PATH:~/apps/bin" >> ~/.bashrc
source ~/.bashrc
{% endhighlight %}

Now if we place a file in `~/apps/bin` and make it executable, we can run it by name from any location.

## USEARCH

[USEARCH ](http://drive5.com/usearch/) is similar to [BLAST](http://en.wikipedia.org/wiki/BLAST), but much, much faster and more versatile. We use it to align the assembled contigs with proteins from a reference species.

Go to [the USEARCH website](http://www.drive5.com/usearch/download.html) and register to download the latest version of USEARCH for your operating system. You'll receive an email that contains a link. Run the following commands to install USEARCH, making sure to put the download link you were sent in place of the one I've got here:

{% highlight bash %}
# change to the apps directory
cd ~/apps
# download the remote file to a local file called 'usearch'
wget -O usearch http://drive5.com/cgi-bin/upload3.py?license=201310190445061132
# make the 'usearch' file executable
chmod +x usearch
# create a symbolic link to the file in the bin directory
ln -s usearch ~/apps/bin/usearch
{% endhighlight %}

Now, you should be able to run `usearch` in the terminal and see some output like this:

{% highlight bash %}
usearch v7.0.1001_i86linux32, 4.0Gb RAM (32.9Gb total), 8 cores
(C) Copyright 2013 Robert C. Edgar, all rights reserved.
http://drive5.com

Licensed to: rds45@cam.ac.uk
{% endhighlight %}

## Bowtie 2

[Bowtie 2](http://bowtie-bio.sourceforge.net/bowtie2/index.shtml) is used to align reads to the assembled transcriptome. We'll follow a similar procedure to the one we used for USEARCH.

Go to [the download site](http://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.1.0/) and locate the latest version for your operating system. Right-click the link and choose 'copy link address'. Now run the following commands in the terminal, substituting the link you just copied for the one I've used if necessary:

{% highlight bash %}
# change to the apps directory
cd ~/apps
# download the bowtie2 zip to bowtie2.zip
wget -O bowtie2.zip http://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.1.0/bowtie2-2.1.0-linux-x86_64.zip/download
# extract
unzip bowtie2.zip
# symlink all the necessary executables to bin
ln -s bowtie2-2.1.0/bowtie2-build ~/apps/bin/bowtie2-build
ln -s bowtie2-2.1.0/bowtie2-inspect ~/apps/bin/bowtie2-inspect
ln -s bowtie2-2.1.0/bowtie2-align ~/apps/bin/bowtie2-align
ln -s bowtie2-2.1.0/bowtie2 ~/apps/bin/bowtie2
{% endhighlight %}

Now, you should be able to run `bowtie2 --version` in the terminal and see some output like:

{% highlight bash %}
/home/rds45/apps/bowtie2-2.1.0/bowtie2-align version 2.1.0
64-bit
Built on do-dmxp-mac.win.ad.jhu.edu
Tue Feb 26 13:34:02 EST 2013
Compiler: gcc version 4.1.2 20080704 (Red Hat 4.1.2-54)
Options: -O3 -m64 -msse2 -funroll-loops -g3
Sizeof {int, long, long long, void*, size_t, off_t}: {4, 8, 8, 8, 8, 8}
{% endhighlight %}

## eXpress

[eXpress](http://bio.math.berkeley.edu/eXpress/overview.html) is used to estimate how much support each contig has based on the read alignments.

Again, the procedure is similar...

Go to the [eXpress website](http://bio.math.berkeley.edu/eXpress/) and hover over the 'Download' menu item. Right-click on the link for your operating system in the drop-down menu, and choose 'Copy Link Address'.

Now run the following in the terminal, substituting in your copied link and filename if necessary

{% highlight bash %}
# change to apps directory
cd ~/apps
# download the tarred, gzipped file
wget http://bio.math.berkeley.edu/eXpress/downloads/express-1.4.1/express-1.4.1-linux_x86_64.tgz
# extract the contents
tar xvf express-1.4.1-linux_x86_64.tgz
# change to the extracted directory
cd express-1.4.1-linux_x86_64
# make the file executable
chmod +x express
# symlink to bin
ln -s express ~/bin/express
{% endhighlight %}

Now, you should be able to run `express -h` and see some output that starts similar to this:

{% highlight bash %}
express v1.4.0
-----------------------------
File Usage:  express [options] <target_seqs.fa> <hits.(sam/bam)>
Piped Usage: bowtie [options] -S <index> <reads.fq> | express [options] <target_seqs.fa>
{% endhighlight %}

Congratulations! You've installed all the dependencies.

## Running transrate

Finally, you can run transrate! To get help in the terminal, run `transrate --help`. You should see:

{% highlight bash %}
Transrate v0.0.1a by Richard Smith <rds45@cam.ac.uk>

DESCRIPTION:
Analyse a de-novo transcriptome
assembly using three kinds of metrics:

1. contig-based
2. read-mapping
3. reference-based

Please make sure USEARCH and bowtie2 are both installed
and in the PATH.

Bug reports and feature requests at:
http://github.com/blahah/transrate

USAGE:
transrate <options>

OPTIONS:
    --assembly, -a <s>:   assembly file in FASTA format
   --reference, -r <s>:   reference proteome file in FASTA format
        --left, -l <s>:   left reads file in FASTQ format
       --right, -i <s>:   right reads file in FASTQ format
  --insertsize, -n <i>:   mean insert size (default: 200)
    --insertsd, -s <i>:   insert size standard deviation (default: 50)
     --threads, -t <i>:   number of threads to use (default: 8)
         --version, -v:   Print version and exit
            --help, -h:   Show this message
{% endhighlight %}

If you need any further help, please [post to the help group](https://groups.google.com/forum/#!forum/transrate-users), or leave a comment below.