# 맨 윗줄에 이 경로를 추가/수정하세요. (님 컴퓨터의 optee_os 경로)
TA_DEV_KIT_DIR = /home/cheonsh/Linux_for_Tegra/public_sources/Linux_for_Tegra/source/public/nvidia-jetson-optee-source/optee/build/t194/export-ta_arm64
CFG_TEE_TA_LOG_LEVEL ?= 4
CPPFLAGS += -DCFG_TEE_TA_LOG_LEVEL=$(CFG_TEE_TA_LOG_LEVEL)

# The UUID for the Trusted Application
BINARY=7fc5c039-0542-4ee1-80af-b4eab2f1998d

-include $(TA_DEV_KIT_DIR)/mk/ta_dev_kit.mk

ifeq ($(wildcard $(TA_DEV_KIT_DIR)/mk/ta_dev_kit.mk), )
clean:
	@echo 'Note: $$(TA_DEV_KIT_DIR)/mk/ta_dev_kit.mk not found, cannot clean TA'
	@echo 'Note: TA_DEV_KIT_DIR=$(TA_DEV_KIT_DIR)'
endif
