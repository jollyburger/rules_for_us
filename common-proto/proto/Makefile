#basic 
GO = protoc -I ${GOPATH}/src/common-proto
PROTO_DIR = ${GOPATH}/src/common-proto
SERV_DIR_PREFFIX = ./common_

#proto files
ECHO_PROTO = echo.proto

all: get_echo
	    sed -i 's/import common \".\"/import common \"vp-public-pb-proto\/proto\/common\"/g' ./*/*/*

get_echo:
	    mkdir -p $(SERV_DIR_PREFFIX)echo
		    $(GO) --go_out=$(SERV_DIR_PREFFIX)echo $(PROTO_DIR)/proto/$(ECHO_PROTO)

