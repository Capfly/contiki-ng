CONTIKI_PROJECT = mqtt-client
all: $(CONTIKI_PROJECT)

CONTIKI = ../..

include $(CONTIKI)/Makefile.dir-variables
MODULES += $(CONTIKI_NG_APP_LAYER_DIR)/mqtt

-include $(CONTIKI)/Makefile.identify-target

MODULES_REL += arch/platform/$(TARGET)

include ../../wolfssl/Makefile.wolfssl

#TODO should use PROJECT_SOURCEFILES but can't because of unresolved math dependencies againt contiki
#PROJECT_SOURCEFILES += $(wolfssl_src)
CONTIKI_SOURCEFILES += $(wolfssl_src)

#PLATFORMS_ONLY = cc26x0-cc13x0 cc2538dk openmote zoul native simplelink cooja

include $(CONTIKI)/Makefile.include
