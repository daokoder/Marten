CFLAGS  = -W -Wall -I.. -pthread -g -pipe $(COPT)
DLL_FLAGS = -DLUA_COMPAT_ALL -I../lua-5.2.1/src

ifeq ($(OS),Windows_NT)
else
  UNAME_S := $(shell uname -s)
  DLL_FLAGS += -shared

  ifeq ($(UNAME_S),Linux)
    CFLAGS += -ldl
  endif

  ifeq ($(UNAME_S),Darwin)
    #  DLL_FLAGS += -bundle -undefined dynamic_lookup -dynamiclib
    DLL_FLAGS += -flat_namespace -undefined suppress -dynamiclib
  endif
endif

all: hello upload post websocket chat lua_dll

hello:
	$(CC) $(CFLAGS) hello.c ../marten.c  -o $@

upload:
	$(CC) $(CFLAGS) upload.c ../marten.c -o $@

post:
	$(CC) $(CFLAGS) post.c ../marten.c -o $@

websocket:
	$(CC) $(CFLAGS) -DUSE_WEBSOCKET websocket.c ../marten.c -o $@

chat:
	$(CC) $(CFLAGS) chat.c ../marten.c -o $@

lua_dll:
	$(CC) $(CFLAGS) $(DLL_FLAGS) lua_dll.c -o $@.so


MSVC    = ../../vc6
CL      = $(MSVC)/bin/cl
CLFLAGS = /MD /TC /nologo $(DBG) /W3 /DNO_SSL \
        /I$(MSVC)/include /I.. /Dsnprintf=_snprintf
LFLAGS  = /link /incremental:no /libpath:$(MSVC)/lib /machine:IX86

windows:
	$(CL) upload.c ../marten.c $(CLFLAGS) $(LFLAGS)
	$(CL) hello.c ../marten.c $(CLFLAGS) $(LFLAGS)
	$(CL) upload.c ../marten.c $(CLFLAGS) $(LFLAGS)
	$(CL) post.c ../marten.c $(CLFLAGS) $(LFLAGS)
	$(CL) post.c ../marten.c $(CLFLAGS) $(LFLAGS)
	$(CL) /DUSE_WEBSOCKET websocket.c ../marten.c $(CLFLAGS) $(LFLAGS)
#$(CL) lua_dll.c $(CLFLAGS) $(DLL_FLAGS) /DLL $(LFLAGS) /SUBSYSTEM:WINDOWS /ENTRY:luaopen_lua_dll /EXPORT:luaopen_lua_dll /out:lua_dll.dll

clean:
	rm -rf hello upload post websocket chat *.exe *.dSYM *.obj .*o
