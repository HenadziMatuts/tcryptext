# tcryptext (tcrypt Extended) kernel module

It is a stand alone version of linux Crypto API _tcrypt_ module. The one can modify sources to test self-developed algorithms. It is also possible to test algorithms already registered in kernel as with usual _tcrypt_.

## Building

Just `make` it!

## Running

To run type `sudo insmod tcryptext [param=value param=...]`.

There are five optional parametres that could be provided to that module:

* _mode_ (int): run specific test. See _tcrypt.c:do_test():1025_ for conreete values. Supresses _alg_, _type_ and _mask_ parametres if provided. Defaults to 0
* _alg_ (string): specific algorithm name. If _mode_ parameter value equals 0, checks if the algorithm with specified name, _type_ and _mask_ exists in kernel. Defaults to null
* _type_, _mask_ (uints): type and mask of the algorithm to check. See some *crypto_alloc_\** function definition for details. Both defaults to 0
* _sec_ (uint): length in seconds of speed tests (defaults to zero which uses CPU cycles instead)