# Authentication

End-user authentication can be handled in three ways within the eSuite platform. 

The first, and most traditional, is the concept of requesting your customer to provide their email address and password and eSuite is able to verify they are who they say they are and provide a session if the details match. We refer to this concept as eSuite as Primary IdAM.

The second is the idea that the eSuite platform is not your primary IdAM platform and end-user authentication is being handled by another system. For this type of authentication, we provide a field named ClientUserId which allows you to store a unique value for each account in the platform. If the end-user then provides the primary IdAM system with valid credentials, that system, in turn, calls eSuite and providing eSuite has an account with the ClientUserId associated a valid session is returned. This concept is referred to as Third-party IdAM.

The final option, similar to the above, is the concept of using SSO. eSuite has integrated against a number of providers to allow end-users to use accounts with another system to authenticate with eSuite. The providers supported by eSuite currently are Facebook, Google + and Yahoo Japan.
