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

- One database per service
- A "Shared Database, Separate Schemas" approach will be used, therefore there is no need right now to take care of multi-tenancy.  
  (See "Multi-Tenant Data Architecture" in the [references](#references) )
- Lowercase - all fields are lowercase.
- The following fields are mandatory for each record:
    - `created_at`
    - `modified_at`
    - `created_by`
    - `modified_by`
- All change scripts are stored in each project, following the approach of https://flywaydb.org/
    
    
## References
### Multi tenant architeture
- [Multi-Tenant Data Architecture](https://msdn.microsoft.com/en-us/library/aa479086.aspx)

### Schema migration / management

- https://blog.codinghorror.com/get-your-database-under-version-control/
- http://stackoverflow.com/questions/175451/how-do-you-version-your-database-schema
- http://martinfowler.com/articles/evodb.html

### Schema migration - tools

- https://github.com/mbryzek/schema-evolution-manager
- https://flywaydb.org/
