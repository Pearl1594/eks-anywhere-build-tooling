BASE_DIRECTORY:=$(shell git rev-parse --show-toplevel)
GIT_TAG:=$(shell cat GIT_TAG)

REPO_OWNER=tinkerbell
REPO=tinkerbell-chart

REPO_NO_CLONE=true

HELM_DIRECTORY=chart
HELM_SOURCE_REPOSITORY=.
HELM_DESTINATION_REPOSITORY=$(REPO_OWNER)/$(REPO)
IMAGE_TAG=$(GIT_TAG)
REQUIRES_CONFIG_FILE=false

BUILD_TARGETS=build-chart
RELEASE_TARGETS=publish-chart

include $(BASE_DIRECTORY)/Common.mk

.PHONY: verify
verify:
	scripts/verify.sh $(HELM_DIRECTORY) $(GIT_TAG)

.PHONY: build-chart
build-chart: verify
	$(BUILD_LIB)/helm_copy.sh $(HELM_SOURCE_REPOSITORY) $(HELM_DESTINATION_REPOSITORY) $(HELM_DIRECTORY) $(OUTPUT_DIR)
	$(BUILD_LIB)/helm_build.sh $(OUTPUT_DIR) $(HELM_DESTINATION_REPOSITORY)

.PHONY: publish-chart
publish-chart: build-chart
	$(BUILD_LIB)/helm_push.sh $(IMAGE_REPO) $(HELM_DESTINATION_REPOSITORY) $(IMAGE_TAG) $(OUTPUT_DIR)


########### DO NOT EDIT #############################
# To update call: make add-generated-help-block
# This is added to help document dynamic targets and support shell autocompletion
# Run make help for a formatted help block with all targets
include Help.mk
########### END GENERATED ###########################
