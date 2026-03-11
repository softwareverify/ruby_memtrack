I'm adding these files here for historical context. It didn't occur to me that people might be interested in these on Github until a few days ago. Previously they have been listed on our website.

These files were the Ruby Memory Tracking API we wrote for [Ruby Memory Validator](https://www.softwareverify.com/product/memory-validator/) in the early 2000s.

**memtrack.c/h** implement wrapper functions that call the worker functions in a modified version of Ruby's **gc.c**.

**Memory profiler API**:  
- rb_set_object_tracing_hook() to set a memory tracing hook.  
- rb_get_object_tracing_hook() to inspect a memory tracing hook.  
- rb_get_heap_roots() to get the Ruby heap roots.   
- rb_get_referenced_objects() to get objects referenced by a specific object.  

**Functions for gc.c to call**:  
- _mem_track_track_allocate()  
- _mem_track_track_deallocate()  

**New functions in gc.c**:  
- _gc_get_referenced_objects()  
- _gc_get_roots()  
- _gc_isValidRubyObject()  
- _gc_addObject()  
- _gc_getReferencedHashTableIterator()  
- _gc_addHashTable()  
- _gc_markLocationsArray()  
