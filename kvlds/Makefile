.POSIX:
PROG=kivaloo-kvlds
SRCS=main.c dispatch.c dispatch_mr.c dispatch_nmr.c btree.c btree_balance.c btree_cleaning.c btree_mlen.c btree_sync.c btree_find.c btree_mutate.c btree_node.c btree_node_split.c btree_node_merge.c serialize.c node.c elasticarray.c kvldskey.c kvhash.c kvpair.c ptrheap.c timerqueue.c elasticqueue.c seqptrmap.c pool.c asprintf.c daemonize.c humansize.c monoclock.c sock.c warnp.c crc32c.c events_immediate.c events_network.c events_timer.c events.c network_buf.c network_accept.c netbuf_read.c netbuf_write.c wire_packet.c wire_readpacket.c wire_writepacket.c wire_requestqueue.c proto_lbs_client.c proto_kvlds_server.c
IDIRS=-I ../lib/datastruct -I ../lib/util -I ../lib/alg -I ../lib/events -I ../lib/network -I ../lib/netbuf -I ../lib/wire -I ../lib/proto_lbs -I ../lib/proto_kvlds
LDADD=-lrt

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
dispatch_mr.o: dispatch_mr.c
dispatch_nmr.o: dispatch_nmr.c
btree.o: btree.c
btree_balance.o: btree_balance.c
btree_cleaning.o: btree_cleaning.c
btree_mlen.o: btree_mlen.c
btree_sync.o: btree_sync.c
btree_find.o: btree_find.c
btree_mutate.o: btree_mutate.c
btree_node.o: btree_node.c
btree_node_split.o: btree_node_split.c
btree_node_merge.o: btree_node_merge.c
serialize.o: serialize.c
node.o: node.c
elasticarray.o: ../lib/datastruct/elasticarray.c
kvldskey.o: ../lib/datastruct/kvldskey.c
kvhash.o: ../lib/datastruct/kvhash.c
kvpair.o: ../lib/datastruct/kvpair.c
ptrheap.o: ../lib/datastruct/ptrheap.c
timerqueue.o: ../lib/datastruct/timerqueue.c
elasticqueue.o: ../lib/datastruct/elasticqueue.c
seqptrmap.o: ../lib/datastruct/seqptrmap.c
pool.o: ../lib/datastruct/pool.c
asprintf.o: ../lib/util/asprintf.c
daemonize.o: ../lib/util/daemonize.c
humansize.o: ../lib/util/humansize.c
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
wire_requestqueue.o: ../lib/wire/wire_requestqueue.c
proto_lbs_client.o: ../lib/proto_lbs/proto_lbs_client.c
proto_kvlds_server.o: ../lib/proto_kvlds/proto_kvlds_server.c
