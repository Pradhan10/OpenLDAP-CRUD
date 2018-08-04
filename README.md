# OpenLDAP-CRUD
Create, read, update and delete operations on LDAP implementation for *nix OpenLDAP

Use command 
sudo ldapmodify -Y EXTERNAL -H ldapi:/// -f index.ldif 
to add a column to olcDbIndex. 

Prerequisite to adding a column for indexing in OpenLDAP under Ubuntu.
The version 2.4.46 of debian maintained OpenLDAP does not includes 
olcRootDN : cn=config,cn=admin
olcRootPW : {SHA}(Your hased password)

In order to run above command and make changes to cn=config file, first add these two attributes to your /etc/ldap/slap.d/cn=config directory, using ldapmodify utility. Otherwise you'll not be able to make changes to cn=config files even if you supply right credentials.

The commonly faced errors are : 
1 : # server is unwilling to perform

2 : # Insufficient access

3 : # invalidCredentials (49)

4 : # insufficientAccessRights (50)

5 : # noSuchObject (32)

Refer link for more information : https://gos.si/blog/installing-openldap-on-debian-squeeze-with-olc/
Useful link for converting schema file to ldif file : https://hnayablog.wordpress.com/2017/12/12/convert-schema-file-to-ldif/
