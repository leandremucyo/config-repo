# Spring CLI Notes

 - Installation
 	
 	curl -s "https://get.sdkman.io" | bash
 	source "$HOME/.sdkman/bin/sdkman-init.sh"
 	sdk install springboot 					#Installs the latest version
 	sdk list springboot						#Shows the versions available
 	sdk install springboot 2.0.0.RELEASE 	#Installs springboot 2.0.0.RELEASE
 	sdk install springboot 2.0.1.RELEASE 	#Installs new version. May prompted to use the new version as default
 	sdk use springboot $DESIRED_VERSION		#To switch from defferent versions
 	#verify spring installation spring --version

 - Installing Java Cryptography Extension

 	#Download jce_policy-8.zip | expand
 	curl -k -LO "http://download.oracle.com/otn-pub/java/jce/8/jce_policy-8.zip" -H 'Cookie: oraclelicense=accept-securebackup-cookie' 
    unzip jce_policy-8.zip
    rm jce_policy-8.zip 					#Remove the zip
    cp -v /tmp/UnlimitedJCEPolicyJDK8/*.jar $JAVA_HOME/jre/lib/security/ ##
 - Starting configserver for speeded encryption/decryption of sensitive information during development configuration values

 	spring cloud configserver
 	spring encrypt --key=$ENCRYPT_KEY property
 	spring decrypt --key=$ENCRYPT_KEY encrypted_property