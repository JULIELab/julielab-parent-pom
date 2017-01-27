# julielab-parent-pom
The top Maven Parent POM for all JULIE Lab projects.

Note that this parent POM defines two different distribution management elements, one for the internal JULIE Lab Nexus and one for the public Sonatype Nexus. Without specifying a profile, the deployment will fail with the message that the repository element was not wrapped into a distribution management element which just reflects the fact that no distribution managament was activated for build at all.

The two profiles are denoted by *julie-nexus-deployment* and *sonatype-nexus-deployment*, respectively.

You can define a default profile to be used by adding it to your <tt>settings.xml</tt> file like this

     <activeProfiles>
        ...
        <activeProfile>julie-nexus-deployment</activeProfile>
        ...
      </activeProfiles>
      
Please be careful when using the *sonatype-nexus-deployment* profile as a default. Artefacts which have been deployed to Sonatype unintentionally are not easily deleted. It is safer to use the internal repository as a default deployment target and just create project-specific exceptions where required.
