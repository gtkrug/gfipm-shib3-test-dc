# gfipm-shib3-test-dc
A very simple Shibboleth 3.1 data connector that implements an extremely simple model of reading attributes from files on the filesystem.  It is configured with an attribute name that is sourced for the filename and a path to the directory that contains the attribute files.

Here is a sample of how to initialize the dataconnector (note the two configuration elements *pathToAttributeFiles* and *uidAttribute*):

    <resolver:DataConnector id="GfipmTest" xsi:type="gfipm:Test" 
                            xmlns="urn:global:gfipm:1.2:resolver"
                            pathToAttributeFiles="/opt/idp3/users/"
                            uidAttribute="LocalId">
        <resolver:Dependency ref="LocalId" />
    </resolver:DataConnector>

Be aware that you must add this classpath snippet to the schema location of your Shibboleth Attribute Resolver:
 
   <resolver:AttributeResolver
        ...[snipped]...
        xmlns:gfipm="urn:global:gfipm:1.2:resolver"
        xsi:schemaLocation=" ... snipped ...
                            urn:global:gfipm:1.2:resolver classpath:/schema/gfipm-1.2-resolver.xsd">
 

