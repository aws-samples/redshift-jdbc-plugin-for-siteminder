## redshift-jdbc-plugin-for-siteminder

## Features
* Provides an implementation for an IAM Siteminder plugin. Once the project is built with Gradle, the
sample Siteminder class will be ready to use with redshift JDBC driver. This working example of a IAM SAML plugin
can be of guidance in developing your own custom plugin.


## Building From Source

Gradle build scripts are provided inside the redshift-jdbc-plugin package.
You can build using the following command:

$> <Path_To_redshift-jdbc-plugin_Package> gradle build

Once built, you will find a jar file inside the 'redshift-jdbc-plugin/build/libs' directory.

## Using the new plugin

This plugin jar must be used together with the version of redshift JDBC driver.
You will also need to add the following aws-sdk dependencies in the classpath:
```
aws-java-sdk-core-1.11.595.jar
aws-java-sdk-sts-1.11.118.jar
commons-codec-1.10.jar
commons-logging-1.1.3.jar
httpclient-4.5.5.jar
httpcore-4.4.9.jar
jackson-annotations-2.6.0.jar
jackson-core-2.6.6.jar
jackson-databind-2.6.6.jar
RedshiftJDBC42-no-awssdk-1.2.36.1060.jar / or any uber jar.
```

## BUILDPATH
all the dependencies + no-aws-sdk driver jar + plugin jar
## CLASSPATH
all the dependencies + no-aws-sdk driver jar + plugin jar
## JDBC CLASS
com.amazon.redshift.jdbc.Driver
## Connection string example
```
jdbc:redshift:iam://<cluster>:<region>/<database>?user=&DbUser=&password=&plugin_name=com.amazon.redshift.plugin.tools.SiteMinderCredentialProvider
```
## Extended Properties
Set the below properties in the SQL client
```
sso_url = SSO URL to connect to AWS
preferred_role = <arn of the IAM role> 

```

Your new plugin class can now be used the same way as all Redshift SAML plugins.
For more details on using the SAML plugins please refer to the Redshift JDBC driver install guide, under 'Configuring IAM Authentication'.


## License

This project is licensed under the Apache-2.0 License.

