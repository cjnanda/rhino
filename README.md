Rhino
=====
Rhino is an open-source implementation of JavaScript written entirely in Java

This project is an unofficial rhino distribution required by wro4j. If you think that your project can benefit from using it, feel free to use it as well. 

Since there wasn't any release for a long time, I decided to perform a release from the latest master branch. The released version has no patch applied and uses original sources as is. This project is useful until an official rhino release is available.

I've tested it with a large suite of tests (in wro4j-extensions module) and everything seems to work fine. If you have any issues, please open an issue or just let me know.

Latest version:  *1.7R5-20130223-1*

Usage
=====
Include the following dependency to pom.xml:

    <dependency>
        <groupId>ro.isdc.wro4j</groupId>
        <artifactId>rhino</artifactId>    
        <version>1.7R5-20130223-1</version>
    </dependency> 
    
Notice that the groupId is not the same as official one and the version uses the following convention:

    ${rhino.version}-${timestamp}-${patch}

  - ${rhino.version} - is the unofficial version of rhino (1.7R5)
  - ${timestamp} - the timestamp of the last commit from master branch (a kind of snapshot) from where the release was performed.
  - ${patch} - patch version (this segment will not always exist, only when a change is required).

Releasing
=====
If the project is checked out for the first time, run:

    git submodule init

which will initialize the rhino git submodule.
After that, fetch the latest sources from rhino official git repo:

    git submodule update

At this point, the release can be performed using latest sources.

Run the following command

    mvn clean deploy -Psonatype-oss-release
