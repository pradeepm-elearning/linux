$file /sbin/init

$java -version

------------------------------------------------------------------------------------------
NOTE: 
If you have OpenJDK installed on your system,
you have the wrong vendor version of Java installed for this exercise.

Completely remove the OpenJDK/JRE from your System.
$sudo apt-get purge openjdk-\*
This command will completely remove OpenJDK/JRE from your system.
This will prevent system conflicts and confusion between different vendor versions of Java. 
-------------------------------------------------------------------------------------------

$sudo mkdir -pv /opt/java

$cd ~/Downloads

$sudo cp -frv jdk-7u51-linux-x64.tar.gz /opt/java  ---> JDK

$cd /opt/java

$sudo tar -xvzf jdk-7u51-linux-x64.tar.gz ---> JDK

$sudo vim /etc/profile
+++++++++++++++JDK+++++++++++++++++
-------------------------------------------------
JAVA_HOME=/opt/java/jdk1.7.0_51
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin

JRE_HOME=/opt/java/jdk1.7.0_51/jre
PATH=$PATH:$HOME/bin:$JRE_HOME/bin

export JAVA_HOME
export JRE_HOME
export PATH
-------------------------------------------------
Save the “/etc/profile” file & exit.

$sudo update-alternatives --install "/usr/bin/java" "java" "/opt/java/jdk-11.0.12/jre/bin/java" 1
$sudo update-alternatives --install "/usr/bin/javac" "javac" "/opt/java/jdk-11.0.12/bin/javac" 1
$sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/opt/java/jdk-11.0.12/bin/javaws" 1

$sudo update-alternatives --set java /opt/java/jdk-11.0.12/jre/bin/java
$sudo update-alternatives --set javac /opt/java/jdk-11.0.12/bin/javac
$sudo update-alternatives --set javaws /opt/java/jdk-11.0.12/bin/javaws

$. /etc/profile