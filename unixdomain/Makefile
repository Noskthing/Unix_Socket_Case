include ../Makefile.defines

PROGS = unixbind unixstrsrv unixstrcli unixdgsrv unixdgcli openfile mycat \
	unixstrsrvcred unixstrclicred

all: ${PROGS}

unixbind: unixbind.o
	${CC} ${CFLAGS} -o $@ unixbind.o ${LIBS}

unixstrsrv: unixstrsrv.o sigchldwaitpid.o
	${CC} ${CFLAGS} -o $@ unixstrsrv.o sigchldwaitpid.o ${LIBS}

unixstrcli: unixstrcli.o
	${CC} ${CFLAGS} -o $@ unixstrcli.o ${LIBS}

unixdgsrv: unixdgsrv.o
	${CC} ${CFLAGS} -o $@ unixdgsrv.o ${LIBS}

unixdgcli: unixdgcli.o
	${CC} ${CFLAGS} -o $@ unixdgcli.o ${LIBS}

openfile: openfile.o
	${CC} ${CFLAGS} -o $@ openfile.o ${LIBS}

mycat: mycat.o myopen.o
	${CC} ${CFLAGS} -o $@ mycat.o myopen.o ${LIBS}

unixstrsrvcred : unixstrsrv.o sigchldwaitpid.o strechocred.o readcred.o
	${CC} ${CFLAGS} -o $@ unixstrsrv.o sigchldwaitpid.o strechocred.o \
		readcred.o ${LIBS}

unixstrclicred : unixstrclicred.o
	${CC} ${CFLAGS} -o $@ unixstrclicred.o ${LIBS}

clean: 
	rm -f ${PROGS} ${CLEANFILES}


