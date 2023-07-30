1. Service Registration: When a service starts up or becomes available, it registers itself with the [[service registry]] by providing its metadata, typically during initialization.
    
2. Service Discovery: When a [[Client]] or application requires access to a particular service, it queries the [[service registry]] through a [[Service Discovery]] client, asking for the location of the desired [[Backend Service|service]].
    
3. Service Resolution: The [[service registry]] responds to the service discovery query with the necessary information about the available instances of the requested service.
    
4. Service Communication: The [[Client]] can then use the obtained service location to communicate directly with the desired service and perform the required operations.

#ServiceDiscovery 