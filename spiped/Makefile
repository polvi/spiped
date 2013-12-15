.POSIX:
PROG=spiped
MAN1=spiped.1
SRCS=main.c dispatch.c proto_conn.c proto_crypt.c proto_handshake.c proto_pipe.c sha256.c elasticarray.c ptrheap.c timerqueue.c dnsthread.c asprintf.c daemonize.c entropy.c monoclock.c noeintr.c sock.c sock_util.c warnp.c events_immediate.c events_network.c events_timer.c events.c network_accept.c network_buf.c network_connect.c crypto_aesctr.c crypto_dh.c crypto_dh_group14.c crypto_entropy.c crypto_verify_bytes.c
IDIRS=-I ../proto -I ../lib/alg -I ../lib/datastruct -I ../lib/dnsthread -I ../lib/util -I ../lib/events -I ../lib/network -I ../lib/crypto
LDADD_REQ=-lcrypto -lpthread

all:	${PROG}

install:${PROG}
	mkdir -p ${BINDIR}
	cp ${PROG} ${BINDIR}/_inst.${PROG}.$$$$_ &&	\
	    strip ${BINDIR}/_inst.${PROG}.$$$$_ &&	\
	    chmod 0555 ${BINDIR}/_inst.${PROG}.$$$$_ && \
	    mv -f ${BINDIR}/_inst.${PROG}.$$$$_ ${BINDIR}/${PROG}
	if ! [ -z "${MAN1DIR}" ]; then			\
		for MPAGE in ${MAN1}; do						\
			cp $$MPAGE ${MAN1DIR}/_inst.$$MPAGE.$$$$_ &&			\
			    chmod 0444 ${MAN1DIR}/_inst.$$MPAGE.$$$$_ &&		\
			    mv -f ${MAN1DIR}/_inst.$$MPAGE.$$$$_ ${MAN1DIR}/$$MPAGE;	\
		done;									\
	fi

clean:
	rm -f ${PROG} ${SRCS:.c=.o}

${PROG}:${SRCS:.c=.o}
	${CC} -o ${PROG} ${SRCS:.c=.o} ${LDADD_EXTRA} ${LDADD_REQ} ${LDADD_POSIX}

main.o: main.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c main.c -o main.o
dispatch.o: dispatch.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c dispatch.c -o dispatch.o
proto_conn.o: ../proto/proto_conn.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../proto/proto_conn.c -o proto_conn.o
proto_crypt.o: ../proto/proto_crypt.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../proto/proto_crypt.c -o proto_crypt.o
proto_handshake.o: ../proto/proto_handshake.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../proto/proto_handshake.c -o proto_handshake.o
proto_pipe.o: ../proto/proto_pipe.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../proto/proto_pipe.c -o proto_pipe.o
sha256.o: ../lib/alg/sha256.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/alg/sha256.c -o sha256.o
elasticarray.o: ../lib/datastruct/elasticarray.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/datastruct/elasticarray.c -o elasticarray.o
ptrheap.o: ../lib/datastruct/ptrheap.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/datastruct/ptrheap.c -o ptrheap.o
timerqueue.o: ../lib/datastruct/timerqueue.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/datastruct/timerqueue.c -o timerqueue.o
dnsthread.o: ../lib/dnsthread/dnsthread.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/dnsthread/dnsthread.c -o dnsthread.o
asprintf.o: ../lib/util/asprintf.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/asprintf.c -o asprintf.o
daemonize.o: ../lib/util/daemonize.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/daemonize.c -o daemonize.o
entropy.o: ../lib/util/entropy.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/entropy.c -o entropy.o
monoclock.o: ../lib/util/monoclock.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/monoclock.c -o monoclock.o
noeintr.o: ../lib/util/noeintr.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/noeintr.c -o noeintr.o
sock.o: ../lib/util/sock.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/sock.c -o sock.o
sock_util.o: ../lib/util/sock_util.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/sock_util.c -o sock_util.o
warnp.o: ../lib/util/warnp.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/util/warnp.c -o warnp.o
events_immediate.o: ../lib/events/events_immediate.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/events/events_immediate.c -o events_immediate.o
events_network.o: ../lib/events/events_network.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/events/events_network.c -o events_network.o
events_timer.o: ../lib/events/events_timer.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/events/events_timer.c -o events_timer.o
events.o: ../lib/events/events.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/events/events.c -o events.o
network_accept.o: ../lib/network/network_accept.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/network/network_accept.c -o network_accept.o
network_buf.o: ../lib/network/network_buf.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/network/network_buf.c -o network_buf.o
network_connect.o: ../lib/network/network_connect.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/network/network_connect.c -o network_connect.o
crypto_aesctr.o: ../lib/crypto/crypto_aesctr.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/crypto/crypto_aesctr.c -o crypto_aesctr.o
crypto_dh.o: ../lib/crypto/crypto_dh.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/crypto/crypto_dh.c -o crypto_dh.o
crypto_dh_group14.o: ../lib/crypto/crypto_dh_group14.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/crypto/crypto_dh_group14.c -o crypto_dh_group14.o
crypto_entropy.o: ../lib/crypto/crypto_entropy.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/crypto/crypto_entropy.c -o crypto_entropy.o
crypto_verify_bytes.o: ../lib/crypto/crypto_verify_bytes.c
	${CC} ${CFLAGS} -D_POSIX_C_SOURCE=200809L ${IDIRS} -c ../lib/crypto/crypto_verify_bytes.c -o crypto_verify_bytes.o
