BASE_DIRECTORY:=$(shell git rev-parse --show-toplevel)
GIT_TAG:=$(shell cat GIT_TAG)
GOLANG_VERSION?="1.13"

REPO=kube-rbac-proxy
REPO_OWNER=brancz

BASE_IMAGE_NAME?=eks-distro-minimal-base-nonroot

BINARY_TARGET_FILES=kube-rbac-proxy

include $(BASE_DIRECTORY)/Common.mk


########### DO NOT EDIT #############################
# To update call: make add-generated-help-block
# This is added to help document dynamic targets and support shell autocompletion
# Run make help for a formatted help block with all targets
include Help.mk
########### END GENERATED ###########################
