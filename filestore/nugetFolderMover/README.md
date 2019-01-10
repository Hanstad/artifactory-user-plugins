Artifactory NuGet Folder Mover User Plugin
==========================================

This plugin converts the NuGet packages under the root repository to
be contained in a folder specified by the package name, as in the
following example:

`nuget-local/NHibernate.3.3.1.4000.nupkg` &rarr;
`nuget-local/NHibernate/NHibernate/NHibernate.3.3.1.4000.nupkg`

This plugin has a cron job scheduled to run every **10** seconds.

#### Installation
To install this plugin:
  - Place the script under the master Artifactory instance in the
  `${ARTIFACTORY_HOME}/etc/plugins`
  - Verify in the `${ARTIFACTORY_HOME}/logs/artifactory.log` that the
  plugin loaded correctly
  - Test with a nuGet package inside one of the nuGet local repositories
  to ensure the file is stored in a containing folder (wait long enough for the cron job to be executed)

#### Configuration
In the nugetFolderMover.properties file an array of prefixes can be configured i.e. 

`prefixes = ['org.companyName', 'companyName']`

Adding this makes the plugin remove 'org.companyName' or 'companyName' from the folder structure