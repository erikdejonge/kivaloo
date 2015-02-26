.POSIX:
PROG=kivaloo-lbs
SRCS=main.c dispatch.c dispatch_request.c dispatch_response.c worker.c storage.c storage_findfiles.c storage_util.c disk.c elasticarray.c ptrheap.c timerqueue.c elasticqueue.c asprintf.c daemonize.c hexify.c monoclock.c sock.c warnp.c crc32c.c events_immediate.c events_network.c events_timer.c events.c network_buf.c network_accept.c netbuf_read.c netbuf_write.c wire_packet.c wire_readpacket.c wire_writepacket.c proto_lbs_server.c
IDIRS=-I ../lib/datastruct -I ../lib/util -I ../lib/alg -I ../lib/events -I ../lib/network -I ../lib/netbuf -I ../lib/wire -I ../lib/proto_lbs
LDADD=-lpthread -lrt

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
dispatch.o: dispatch.c
dispatch_request.o: dispatch_request.c
dispatch_response.o: dispatch_response.c
worker.o: worker.c
storage.o: storage.c
storage_findfiles.o: storage_findfiles.c
storage_util.o: storage_util.c
disk.o: disk.c
elasticarray.o: ../lib/datastruct/elasticarray.c
ptrheap.o: ../lib/datastruct/ptrheap.c
timerqueue.o: ../lib/datastruct/timerqueue.c
elasticqueue.o: ../lib/datastruct/elasticqueue.c
asprintf.o: ../lib/util/asprintf.c
daemonize.o: ../lib/util/daemonize.c
hexify.o: ../lib/util/hexify.c
monoclock.o: ../lib/util/monoclock.c
sock.o: ../lib/util/sock.c
warnp.o: ../lib/util/warnp.c
crc32c.o: ../lib/alg/crc32c.c
events_immediate.o: ../lib/events/events_immediate.c
events_network.o: ../lib/events/events_network.c
events_timer.o: ../lib/events/events_timer.c
events.o: ../lib/events/events.c
network_buf.o: ../lib/network/network_buf.c
network_accept.o: ../lib/network/network_accept.c
netbuf_read.o: ../lib/netbuf/netbuf_read.c
netbuf_write.o: ../lib/netbuf/netbuf_write.c
wire_packet.o: ../lib/wire/wire_packet.c
wire_readpacket.o: ../lib/wire/wire_readpacket.c
wire_writepacket.o: ../lib/wire/wire_writepacket.c
proto_lbs_server.o: ../lib/proto_lbs/proto_lbs_server.c
