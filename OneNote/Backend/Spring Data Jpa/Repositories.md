- This is the DAO (data access object) which has direct contact with database - goal is to abstract everything which reduces the amount of boiler-plate code required to implement data access layer - Repository should extend one of these interfaces
    
    - CrudRepository
    - PagingAndSortingRepository
    - JpaRepository
      
    
- **CrudRepository<T,ID>:** - **PagingAndSortingRepository<T,ID>:** - **JpaRepository<T,ID>:**
      

|   |   |
|---|---|
|save(S entity)|Saves a given entity.|
|saveAll(Iterable<S> entities)|Saves all given entities.|
|findById(ID id)|Retrieves an entity by its id.|
|existsById(ID id)|Returns whether an entity with the given id exists.|
|findAll()|Returns all instances of the type.|
|findAllById(Iterable<ID> ids)|- Returns all instances of the type T with the given IDs.<br>- If some or all ids are not found, no entities are returned for these IDs.<br>- Note that the order of elements in the result is not guaranteed.|
|count()|Returns the number of entities available.|
|deleteById(ID id)|Deletes the entity with the given id.|
|delete(T entity)|Deletes a given entity.|
|deleteAllById(Iterable<? extends ID> ids)|Deletes all instances of the type T with the given IDs.|
|deleteAll(Iterable<? extends T> entities)|Deletes the given entities.|
|deleteAll()|Deletes all entities managed by the repository.|
   

|   |   |
|---|---|
|findAll(Pageable pageable)|Returns a Page of entities meeting the paging restriction provided in the Pageable object.|
|findAll(Sort sort)|Returns all entities sorted by the given options.|
   

|   |   |
|---|---|
|flush()|Flushes all pending changes to the database.|
|saveAllAndFlush(Iterable<S> entities)|Saves all entities and flushes changes instantly.|
|saveAndFlush(S entity)|Saves an entity and flushes changes instantly.|
