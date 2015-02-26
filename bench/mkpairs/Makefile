.POSIX:
PROG=kivaloo-mkpairs
SRCS=main.c warnp.c mkpair.c sha256.c
IDIRS=-I ../../lib/util -I ../lib
LDADD=

all:	${PROG}

install:${PROG}
	mkdir -p ${BINDIR}
	cp ${PROG} ${BINDIR}/_inst.${PROG}.$$$$_ &&	\
	    strip ${BINDIR}/_inst.${PROG}.$$$$_ &&	\
	    chmod 0555 ${BINDIR}/_inst.${PROG}.$$$$_ && \
	    mv -f ${BINDIR}/_inst.${PROG}.$$$$_ ${BINDIR}/${PROG}

clean:
	rm -f ${PROG} ${SRCS:.c=.o}

${PROG}:${SRCS:.c=.o}
	${CC} -o ${PROG} ${LDADD} ${SRCS:.c=.o}

${SRCS:.c=.o}:
	${CC} ${CFLAGS} ${IDIRS} -c $<

main.o: main.c
warnp.o: ../../lib/util/warnp.c
mkpair.o: ../lib//mkpair.c
sha256.o: ../lib//sha256.c
