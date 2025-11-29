# Big Picture of Design
![image](mermaid-flow-1x(1).png)

**Concurrency Model**: CRDT
  - Good Offline Support as it is one main concerns
  - No Bottleneck like OT(server-centric)
  - I Choose Yjs as the library which implements CRDT
  - 

**Database**: PostgreSQL
  - Good Support for both Relational and Unstructured(JSONB, BYTEA) data
  - Its Reliable because its ACID compliant
  - MongoDB could be a better option as we are working with Unstructured data but in this design i prefer to use Postgres
    becuase i'm handling Permissions in the same space better option would be using an Identity Server

**Image-Store**: MinIO(s3)
  - Storing Images in DB is not an option and saving on Local Disk is not Scaleable

**Redis**:
  - Can share changes fast and let persisting data on another process 
  - It is Scaleable 

**Trasport**: WebSockets
  - It is Bidrictional
  - Persistent TCP connection will notify server on discontections
