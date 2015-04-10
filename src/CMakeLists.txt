include_directories(SYSTEM ../include/)
add_library(
cyclone
../include/cyclone/cyclone.h
../include/cyclone/precision.h


body.cpp
../include/cyclone/body.h

collide_coarse.cpp
../include/cyclone/collide_coarse.h

collide_fine.cpp
../include/cyclone/collide_fine.h

contacts.cpp
../include/cyclone/contacts.h

core.cpp
../include/cyclone/core.h

fgen.cpp
../include/cyclone/fgen.h

joints.cpp
../include/cyclone/joints.h

particle.cpp
../include/cyclone/particle.h

pcontacts.cpp
../include/cyclone/pcontacts.h

pfgen.cpp
../include/cyclone/pfgen.h

plinks.cpp
../include/cyclone/plinks.h

pworld.cpp
../include/cyclone/pworld.h

random.cpp
../include/cyclone/random.h

world.cpp
../include/cyclone/world.h
)