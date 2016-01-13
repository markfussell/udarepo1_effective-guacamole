
# Virtual Computer Unit

## Summary
This is the synopsis of an introduction to computer-virtualization unit that might be part of a cloud computing or other computer system design program.

## Presentation as video


## Presentation Notes (2016-01-12)

The presentation is relatively "low budget": The first part (up to the eighth minute) has visuals as pretty basic slides with interspersed
mini-quizes and the second part is a screen cast that students could follow along with.  I actually like much more dynamic visuals,
but this is a first structural pass to see if the materials / presentation-order is reasonable.

The voice track was mostly separate from the visuals so they could be easily recomposed.  

There are a few mis-spoken sections "add box" vs. "box add" that are obvious mistakes and would need to be re-recorded to be 'consistent' 

For Part-2 there is not really enough time for a full screen cast, so sections have been elided with a visual transition.
The fuller version is about three-five minutes longer and flows a bit better, but that was beyond the time limit.

There are only placeholders for ending Part-1 and starting Part-2.  I did content for Part-2 instead.


## Initial 'script' / overview

Hi, I am Mark Fussell, a professional software developer.  This unit is about 'computer-virtualization' which is at the heart of many modern technologies including 'cloud computing'.  By
the end of this unit, you should be comfortable with what a 'virtual machine' and a 'virtual computer' are, how they help solve certain problems, and
what part they play within 'cloud computing', 'containers', and other important technologies.

I have been programming computers for several decades, and during that time some things have changed dramatically.
There are many more types and configurations of computers every year: from a Roomba cleaner, through a smart phone, a laptop computer, and the servers
powering google.com.  All these different types of computers are doing many more kinds of things too.  
There is effectively an explosion of computers and an explosion of things they could be doing.

One of the key aspects to successfully understanding and programming computers is to hide unnecessary details.  Computers can have _billions_ of transistors
and millions of lines of code to make them work.  If you have too many details, it will be hard to solve the problem at hand.
Getting rid of details can be done in a number of ways:
 
 * Focus on a very small part of a bigger problem (like the keyboard device driver)
 * Have multiple computers use a similar 'architecture' (Display, Keyboard, Memory, Disk, Network, CPU) so you know what to expect
 * Have multiple computers use exactly the same 'language' (CPU chip)
 * Have a higher-level programming language (say Python) that can be converted into different computer CPU languages.  This is commonly called 'Abstraction'
 
and so on.   

Early on in computer history, the above were among the most common approaches, but there is one more that was prevalent too: create a 'virtual computer' on top of the 'physical computer' that creates a facade of commonality
 even when there are significant physical differences.  Some early languages for which this was done include LISP, Smalltalk, and PASCAL.  A more recent language partially did this: Java is normally implemented with a Java Virtual Machine.
Having a partial 'virtual computer' is how one Java program can run on several different types of computers: Mac, Windows, and Linux.

[Quiz: What are the different types]

Getting rid of details in the different ways mentioned above have different benefits and drawbacks.  

  * You can focus on doing exactly the right thing, but in a very limited context
  * You can standardize an 'architecture' but then it might bloat or limit what a computer can do
  * You can standardize the 'language' of the computer, but then might miss out on new capabilities (e.g. GPUs are better than CPUs for graphics and other processing)
  * You can have a more abstract language, but then it might not run as well or is missing a capability the CPU has
  
[Quiz: What are the different benefits]

Earlier virtual computers had a number of issues: 

  * If the physical technology is too different, they run significantly slower
  * They require a lot of memory to have more than one virtual computer
  * If there are too many different types of technology and virtual computers, they have a network effect (lots of different possibilities)
  * Software itself can be quite expensive, so running multiple copies of it was not cost effective.
  
Over time, things have changed and most of these issues are no longer very significant.  After we go through what a virtual computer is, we can return to the benefits and issues.

[Quiz: Match solution to issue]

So what is a virtual computer?  A true virtual computer is 'in all appearances to the software running on it' indistinguishable from a physical computer.  It appears to have a display, keyboard, memory, disk, network, and so on as
possible devices attached to it.  It appears to be running Windows, iOS, Linux, or other operating systems that talk to the devices.  Python libraries believe they are calling into standard operating system libraries.  And even a human
should not be able to tell the difference if "in the next room".
 
As all computers are not the same, virtual computers do not need to be the same.  Some may have displays, and some not.  And some may have a lot of memory and some little. But that should be indistinguishable from a physical computer having a display or not, and having a certain amount of memory.

[Quiz: How to tell the difference]

The core characteristics to a 'Server' computer is it has:

  * Speed: A CPU of some manufacture and speed (and maybe some number of 'cores')
  * Memory: A certain amount of RAM
  * Disk: One or more disks for storage beyond RAM
  * Network: One or more network connections and its speed
  
A virtual Server computer should these same characteristics.  

With most 'basic' virtualization, a virtual computer lives on a single 'host'.  Because of this, the virtual computer would be

  * Limited in its maximum capabilities by the host computer 
  * Reduced in performance by any virtualization overhead
  * Reduced in performance by limits on it (say the RAM available was forcibly reduced)
  * Reduced in performance by how many virtual computers beyond itself were running
  
One way to visualize virtual computers is they are contained within 'the box' of the host computers capabilities.  Especially for Memory and Disk, this can be a pretty accurate description.

[Boxes]

Virtual Computers were initially a very large tradeoff in benefits to issues.  But a number of things have changed that make for very few issues:

  * Physical CPUs are both very similar and even include virtualization capabilities built-in, so virtualization is not slow
  * Most computers have plenty of memory to do a lot of different things.  The different things can be done on different virtual computers almost as easily as being on the same computer (and with possible benefits).
  * The number of architectures for both 'host' and 'virtual' computers is relatively small and consistent.
  * Software in many cases is completely free.
  
[Then vs. Now]

Now that you have an overview of Virtual Computers, we are going to work with one implementation of Virtual Computers so you can get more familiar with their capabilities. 

The particular implementation will be using Vagrant and VirtualBox, and will be a CentOS-based linux distribution.  CentOS is one of the main linux
distributions and is among the most common to use with Amazon Web Service and Google Compute Engine

Please see the instructions for installing Vagrant on your particular computer.  

```bash
### Add the centos7 'box' to your list of vagrant boxes (or base images for virtual computers)
vagrant box add centos7_1503 https://github.com/holms/vagrant-centos7-box/releases/download/7.1.1503.001/CentOS-7.1.1503-x86_64-netboot.box
vagrant box list

### Now creata an example
mkdir centos7a
cd centos7a
vagrant init centos7_1503
cat Vagrantfile

### Now we have a Virtual Computer on our computer.  We can just launch and connect to it
vagrant up
vagrant ssh
ls
whoami
hostname

```


  