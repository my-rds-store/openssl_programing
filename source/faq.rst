#####
FAQ
#####

One of the primary differences between master (OpenSSL 1.1.0) and the 1.0.2 version is that many types have been made opaque, i.e. applications are no longer allowed to look inside the internals of the structures. The biggest impact on applications is that:


You cannot instantiate these structures directly on the stack. So instead of:

.. code:: cpp

    EVP_CIPHER_CTX ctx;

you must instead do:

.. code:: cpp

    EVP_CIPHER_CTX *ctx = EVP_CIPHER_CTX_new();
    /* 
     do something
    */
    EVP_CIPHER_CTX_free(ctx);

