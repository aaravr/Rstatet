#### Profile service

#### Analysis
Profile service was created as a backend for Data-In and Data-Out services. Whilst the data-in and data-out are profile data model agnostic, profile service is LHS
and RHS data model aware and interacts with the working copy and golden source schema directly. Most of the data retrieval and persistence functionalities for data-in and data-out  
are achieved through alias mapping framework, an abstract layer that allows data access using aliases instead of physical data points.

Functionality provided by profile services are as follows:
* Data retrieval and update:
   * Working copy - Update existing profile
   * Golden Source - Update existing profile
   * Golden source - Create new profile
   * Simple data points  - update simple datapoints
   * Complex data points  - profile
   * Collection data points - profile
   * Connected party data points
   * profile checklists

* Miscellaneous
    * Profile update

* Country mastering update
  * If the update is not done in-memory, no impact on profile service, but a minor suggestion will be to use the orchestrator refresh


Option 1:

Profile service virtualization (no changes to data-in and data-out components):

Pros:
    Leverage existing DVL infrastructure and endpoints implemented for Channel services data virtualization
    Minimal changes compared to implementing a separate data transformation and persistence layer for Data-In and Data-Out

Cons:
    Profile service has to be maintained as a separate component until the completion of domain breakdown activity
    Additional tests required to ensure the JSON serialization/de-serialization works for all nested types




Data retrieval and persistence from Data-In and Data-Out:

Pros:

Cons:
 * Current mappers do not cater for



