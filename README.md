#Plan 9 from the Outer Darkness

A riff on Plan 9 from Outer Space, plus some stuff from NeXTStep/OpenStep and the STEPS VPRI project (ie COLA), plus some tiny influences from LosethOS and Minix.

There is a _lot_ to do.

##Components

- OpenFirmware/Xen basis
- Unicode
- A Riff on Cola + Pepsi
    - Based on a mix of Arc + Common Lisp rather than Scheme
- Port filesystem, plumber, styx/9p2000
- Fonts
- Graphics layer like Quartz + OpenGL ES + Cairo/Pango rather than X
- window manager
- shell - repl from hell
    - HLL rather than the usual shell script
    - Pipes
    - Filesystem union/multi-backed stuff so that you can cat/grep etc without having to go through git etc
    - Completions
    - Graphics + mouse integration
        - Somewhat like (Factor/LosethOS)'s repl, where you can 'print', copy, paste, pipe etc graphics
    - Nice movement keys
    - Editor integration
- vm?
- editor - riff on gvim
- tcp/ip stack
- ssh
- webserver
- web browser
- Port Git
- Self hosting development
  - Editor, VCS etc
  - mk, linker
  - apt-alike
- Display media
- Microkernel? Minix/L4 alike, with resurrection/reincarnation server + heartbeat server?
