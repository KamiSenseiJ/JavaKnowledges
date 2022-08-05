# 1. install openjdk manually on linux

1. download openjdk
    1. go to openjdk web home page
    1. click `"JDK GA/EA Builds"` in left side
    1. choose a `"GA", general availability` version
    1. Builds section, `"Linux/x64"` for common linux, click for download
1. install
    1. `"mkdir -p mylocal/java/jdk"`
    1. `"cd mylocal/java/jdk"`
    1. `"move ~/Downloads/openjdk-18.0.1.1_linux-x64_bin.tar.gz ."` (you may have a different openjdk version)
    1. `tar xf openjdk-18.0.1.1_linux-x64_bin.tar.gz`
1. setting environment variable
    1. edit `~/.bashrc`, put below to the end of it;
    1. `"export JAVA_HOME=/home/j/mylocal/java/jdk/jdk-18.0.1.1"` (you may have a differenct home path)
    1. `"export PATH=$PATH:$JAVA_HOME/bin"`
1. take effect
    1. in current terminal: `source ~/.bashrc`
    1. or, open a new terminal
1. testing with "java --version" command
