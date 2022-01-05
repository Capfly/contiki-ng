CONTIKI_PROJECT = mqtt-client
all: $(CONTIKI_PROJECT)

CONTIKI = ../..

include $(CONTIKI)/Makefile.dir-variables
MODULES += $(CONTIKI_NG_APP_LAYER_DIR)/mqtt

-include $(CONTIKI)/Makefile.identify-target

MODULES_REL += arch/platform/$(TARGET)

include ../../wolfssl/Makefile.wolfssl
include ../../wolfMQTT/Makefile.wolfMQTT
%.d:
	@mkdir -p $(OBJECTDIR)/wolfssl/src
	@mkdir -p $(OBJECTDIR)/wolfssl/wolfcrypt/src
	@mkdir -p $(OBJECTDIR)/wolfMQTT/src

TARGET_LIBFILES += -lm
PROJECT_SOURCEFILES += $(wolfssl_src)
PROJECT_SOURCEFILES += $(wolfMQTT_src)
#TODO should use PROJECT_SOURCEFILES but can't because of unresolved math dependencies againt contiki
#CONTIKI_SOURCEFILES += $(wolfssl_src)
#CONTIKI_SOURCEFILES += $(wolfMQTT_src)

#PLATFORMS_ONLY = cc26x0-cc13x0 cc2538dk openmote zoul native simplelink cooja

include $(CONTIKI)/Makefile.include
