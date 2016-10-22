---
title: DB Design
sub-title: 
dateCreated: "2016-10-21"
createdBy: swr
dateModified: "2016-10-21"
modifiedBy: swr
status: in-progress
---

## General rules

- A "Shared Database, Separate Schemas" approach will be used, therefore there is no need right now to take care of multi-tenancy.  
  (See "Multi-Tenant Data Architecture" in the [references](#references) )
- Lowercase - all fields are lowercase.
- The following fields are mandatory for each record:
    - `date-created`
    - `date-modified`
    - `created-by`
    - `modified-by`
    
    
## References
- [Multi-Tenant Data Architecture](https://msdn.microsoft.com/en-us/library/aa479086.aspx)


