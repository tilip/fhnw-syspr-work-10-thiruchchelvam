# System-Programmierung
## Hands-on zu Lektion 10
Für Slides und Code Beispiele, siehe [Lektion 10](../../../fhnw-syspr/blob/master/10/README.md)

> *Achtung: Arbeiten Sie nicht direkt auf diesem Repository.*<br/>
> *[Erstellen Sie eine persönliche Kopie, mit diesem GitHub Classroom Link](https://classroom.github.com/a/k79VVNgq).*

### a) Message Queues, 15'
* Lesen Sie die folgenden [TLPI](http://man7.org/tlpi/) Beispiel Programme:<pre>
[pmsg_create.c](http://man7.org/tlpi/code/online/book/pmsg/pmsg_create.c.html), [pmsg_getattr.c](http://man7.org/tlpi/code/online/book/pmsg/pmsg_getattr.c.html), [pmsg_unlink.c](http://man7.org/tlpi/code/online/book/pmsg/pmsg_unlink.c.html), [pmsg_send.c](http://man7.org/tlpi/code/online/book/pmsg/pmsg_send.c.html) und [pmsg_receive.c](http://man7.org/tlpi/code/online/book/pmsg/pmsg_receive.c.html)</pre>
* Testen Sie eine Message Queue mit den Kommandos:<pre>
    $ ./pmsg_create -cx /my_mq
    $ ./pmsg_send /my_mq "my msg a" 0 # Prio. 0
    $ ./pmsg_send /my_mq "my msg b" 1 # > 0 => Skip
    $ ./pmsg_receive /my_mq # Blockierend
    $ ./pmsg_unlink /my_mq</pre>
    
### b) Semaphore, 15'
* Lesen Sie die folgenden [TLPI](http://man7.org/tlpi/) Beispiel Programme:<pre>
[psem_create.c](http://man7.org/tlpi/code/online/book/psem/psem_create.c.html), [psem_wait.c](http://man7.org/tlpi/code/online/book/psem/psem_wait.c.html), [psem_getvalue.c](http://man7.org/tlpi/code/online/book/psem/psem_getvalue.c.html), [psem_post.c](http://man7.org/tlpi/code/online/book/psem/psem_post.c.html) und [psem_unlink.c](http://man7.org/tlpi/code/online/book/psem/psem_unlink.c.html)</pre>
* Testen Sie ein Semaphor mit den Kommandos:<pre>
    $ ./psem_create -c /my_sem 600 0
    $ ./psem_wait /my_sem &
    $ ./psem_getvalue /my_sem
    $ ./psem_post /my_sem
    $ ./psem_unlink /my_sem</pre>

### c) Shared Memory, 15'
* Lesen Sie die folgenden [TLPI](http://man7.org/tlpi/) Beispiel Programme:<pre>
[pshm_create.c](http://man7.org/tlpi/code/online/book/pshm/pshm_create.c.html), [pshm_write.c](http://man7.org/tlpi/code/online/book/pshm/pshm_write.c.html), [pshm_read.c](http://man7.org/tlpi/code/online/book/pshm/pshm_read.c.html) und [pshm_unlink.c](http://man7.org/tlpi/code/online/book/pshm/pshm_unlink.c.html)</pre>
* Testen Sie Shared Memory mit den Kommandos:<pre>
    $ ./pshm_create -c /my_shm 0
    $ ls -l /dev/my_shm
    $ ./pshm_write /my_shm "hello"
    $ ./pshm_read /my_shm
    $ ./pshm_unlink /my_shm</pre>
