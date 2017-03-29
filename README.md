# simplesamlphp-immtableid

Filter to generate the AzureAD ImmutableID  attribute.
 
By default, this filter will generate the ID based on the UserID of the current user. This is by default generated from the attribute configured in 'userid.attribute' in the metadata. If this attribute isn't present, the userid will be generated from the eduPersonTargetedID attribute, if it is present.
 
It is possible to generate this attribute from another attribute by specifying this attribute in this configuration.

Example - generate from user ID:
<code>
 'authproc' => array(
    50 => 'immutableid_Auth:ImmutableID',
  )
</code>
 
Example - generate from eduPersonPrincipalName-attribute:
<code>
 'authproc' => array(
    50 => array('class' => 'immutableid_Auth:ImmutableID' , 'attributename' => 'eduPersonPrincipalName'),
  ),
 </code>
