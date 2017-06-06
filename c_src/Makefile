PRIVDIR := ../priv
ERLDIR	:= $(shell erl -noshell -eval "io:format([126,115,126,110],[code:root_dir()])" -s erlang halt)
ERL_C_INCLUDE_DIR := $(ERLDIR)/usr/include

all : $(PRIVDIR)/inpevt_driver.so

override CFLAGS += -fpic -shared -I$(ERL_C_INCLUDE_DIR)

$(PRIVDIR)/inpevt_driver.so : inpevt_driver.o dterm.o
	$(CC) -shared -fpic $(LDFLAGS) -o $@ $^

clean:
	$(RM) -f $(PRIVDIR)/inpevt_driver.so inpevt_driver.o dterm.o
