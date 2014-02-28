Welcome in the SUB''s public Maven repository !
================================================

How to use it
-------------

Add this in your `pom.xml` file:

    <repositories>
        <repository>
            <id>sub-public-snapshots</id>
            <url>https://raw.github.com/subugoe/mvn-repo/master/snapshots</url>
        </repository>
        <repository>
            <id>sub-public-releases</id>
            <url>https://raw.github.com/subugoe/mvn-repo/master/releases</url>
        </repository>
    </repositories>

To deploy in this Maven repository
----------------------------------

Add this in the `pom.xml` of the artifact to be deployed:

     <distributionManagement>
        <repository>
            <id>repo</id>
            <url>https://raw.github.com/subugoe/mvn-repo/master/releases</url>
        </repository>
        <snapshotRepository>
            <id>snapshot-repo</id>
            <url>https://raw.github.com/subugoe/mvn-repo/master/snapshots</url>
        </snapshotRepository>
    </distributionManagement>

Clone the git repository locally :

`$> git clone gitgithub.com:subugoe/mvn-repo.git`

Then deploy the files in your local repo (beware if it is a release or a
snapshot ![][]!):

`$> mvn -DaltDeploymentRepository=snapshot-repo::default::file:PATH_TO/maven-repo/snapshots/ clean deploy`

And commit and push your changes to github:

`$> git commit -m “MESSAGE”`

`$> git push origin master`

Greetings
---------

Thanks to [Cemerick][] for setting up this Maven repository and [Ekito] for this README file tempate.

  []: 
  [Cemerick]: http://cemerick.com/2010/08/24/hosting-maven-repos-on-github/
  [Ekito]: https://github.com/Ekito