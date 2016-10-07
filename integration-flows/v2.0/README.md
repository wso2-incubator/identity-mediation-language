# Identity Mediation Language Samples (NEL v2.0)


## Samples

The following scenarios are demonstrated by the samples,

1. SAML Single Sign On with authentication with Local IDP.
2. SAML Single Sign On with multi-step authentication. (Local IDP + OIDC federation)
3. SAML Single Sign On with multi-step authentication based on user's role. </li>

<br>

### Pre-requisites : 

   * Build the integration server from [here](https://github.com/wso2/product-integration-server) .
   * Set-up the travelocity sample using instructions [here](https://docs.wso2.com/display/IS520/Configuring+Single+Sign-On#ConfiguringSingleSign-On-ConfiguringtheSSOwebapplication).
   * Follow only **Configuring the SSO web application** step in the previous step.
   * Configure the SAMLSSO url as : http://localhost:8290/travelocity/saml
   * Set SAML Response Signing to `false` since we do not support SAML Signature validation yet.
  
   * Build the following packages and copy the jars to `<iserver_home>/osgi/dropins`
       1. authentication-endpoint
       2. authentication-request-builder
       3. authentication-response-processor
       4. identity-bus-framework
       5. oidc-request-builder
       6. oidc-response-processor
       7. saml-request-processor
       8. saml-response-builder
       
   * Copy the dependencies from `dependencies` to `<iserver_home>/osgi/dropins/`
   
         commons-cli_1.2.0.wso2v1.jar
         commons-codec_1.4.0.wso2v1.jar
         commons-collections_3.2.2.wso2v1.jar
         commons-configuration_1.6.0.wso2v1.jar
         commons-dbcp_1.4.0.wso2v1.jar
         commons-fileupload_1.2.2.wso2v1.jar
         commons-httpclient_3.1.0.wso2v2.jar
         commons-io_2.0.0.wso2v2.jar
         commons-io_2.4.0.wso2v1.jar
         commons-lang_2.6.0.wso2v1.jar
         commons-primitives_1.0.0.wso2v1.jar
         commons_lang3_3.3.2_1.0.0.jar
         lang_tag_1.4_1.0.0.jar
         net.minidev.json-smart_1.3.0.jar
         nimbus-jose-jwt_2.26.1.wso2v3.jar
         oauth2_oidc_sdk_4.8_1.0.0.jar
         opensaml2_2.4.1.wso2v1.jar
         tomcat-servlet-api_7.0.59.wso2v1.jar
         wss4j_1.5.11.wso2v11.jar
         xercesImpl-2.8.1.wso2v2.jar
         
    
<br>

#### Sample 1 : SAML Single Sign On with authentication with Local IDP.

How to Setup this sample?
* Copy `integration-flows/v2.0/authenticationEndpoint-v2.xyz` and `integration-flows/v2.0/localauth-v2.xyz` into `<iserver_home>/deployment/integration-flows/`
* Go to http://localhost:8080/travelocity.com/index.jsp
* Use SAML SSO login with `POST binding` option.  

    