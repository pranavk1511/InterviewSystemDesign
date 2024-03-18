# The Interface Segregation Principle 
It states that no client should be forced to depend on methods it does not use. Essentially, it recommends creating more specific interfaces rather than a single, general-purpose interface.

- Purpose: The principle aims to reduce the impact of changes and the complexity of having large, general-purpose interfaces. It promotes the creation of smaller, more focused interfaces.
- Smaller Interfaces: Instead of one large interface, multiple smaller interfaces are preferred, each serving a specific sub-module or client requirement. This means clients will only need to know about the methods that are of interest to them.
- Decoupling: ISP leads to a more decoupled system. Changes in one part of the system are less likely to affect unrelated parts, as clients are not forced to depend on interfaces they do not use.