## Memory Tuning
`postgresql.conf` should be updated to leverage the OS memory. 

- [Parameter tuning guidelines](https://severalnines.com/database-blog/architecture-and-tuning-memory-postgresql-databases#:~:text=The%20default%20value%20of%20shared_buffers%20is%20typically%20128%20megabytes%20(128MB).)

For example, a VM with 32 cores and 128 GB RAM can be
```
shared_buffers: 16GB
temp_buffers: 2GB
work_mem = 32MB
max_connections: 512
maintenance_work_mem=2GB
```
