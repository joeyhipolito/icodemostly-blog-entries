### My Thoughts
I just can't help myself but to blog this, although  it's just been a month since I learned about this. I wanted to talk about it already. 

### What is this all about?
Today I will be talking about **HHVM** or HipHop Virtual Machine for Php, developers of today like to be called hhvm nowadays than hiphop. 
> HipHop for PHP describes a series of PHP execution engines and improvements created by Facebook.

That definition was taken from [wikipedia](http://en.wikipedia.org/wiki/HHVM), because I ain't expert at this, I am actually new to this. But base from what I understand, it compiles php to c++, making it 40% faster?, can't remember where I get that but the thing is it's faster and uses less resources. Great isn't it?

{<1>}![hhvm](/content/images/2013/Nov/hhvm.png)

### Why the hell I am using it?
I know it's a bit hippy and a\*\*h\*le to just for the sake of "Hell yeah, I'm using what *THEY* are using" I am using it, but what's wrong with trying out what they use, that is why it is open-source, so everybody could use it and try it.

Also! another reason I installed it is that I believe it allows you to code simpler, I have a hunch, although I only based this hunch to a test ran by facebook on some popular php frameworks around. Why `Slim` passed 100% and `Codeigniter` did not?, maybe because Slim is much simpler and doesn't contain excessive unecessary code.

### How do I get it?
As I have mentioned, hhvm is open-source and the code base can be found on [facebook's github](https://github.com/facebook/hhvm/). Which pretty have all your needs to get started. But noticed that hhvm cannot run on all enviroments, and I am running it in Ubuntu 13.10.

### How did I installed it?
I've did it the hard way, using the source built package instead of the prebuild package.

1. You have to install the dependency libraries as described [here](https://github.com/facebook/hhvm/wiki/Building-and-installing-HHVM-on-Ubuntu-13.10)
2. I **cd**'ed to my home directory and run this *shell* commands
```
md dev
export CMAKE_PREFIX_PATH=`pwd`
git clone git://github.com/facebook/hhvm.git
cd hhvm
git submodule init
..
git clone git://github.com/libevent/libevent.git
cd libevent
git checkout release-1.4.14b-stable
cat ../hhvm/hphp/third_party/libevent-1.4.14.fb-changes.diff | patch -p1
./autogen.sh
./configure --prefix=$CMAKE_PREFIX_PATH
make
make install
..
cd hhvm
git submodule update
export HPHP_HOME=`pwd`
cmake .
make
```

**note**: notice that that aren't usual *shell* commands because I have set shortcuts in my `.aliases` file. I will be talking about **dotfiles** soon and how did I setup my dev. enviroment.

And finally you just have to create a *symlink* (a shortcut) by doing

```
ln -s dev/hhvm/hphp/hhvm/hhvm /usr/bin/hhvm
```

Now you can access and run `hhvm` on your shell, launch php files and whatsoever.

### Conclusion
HHVM is super awesome, that is my point of view as of today, and it might allow me, although not 100% sure, to code cleaner, simpler and faster. I have also proven myself that having a specific architecture for every project is much efficient that using an functionality bloated frameworks.