#  Copyright (c) 2019 WSO2 Inc. (http:www.wso2.org) All Rights Reserved.
#
#  WSO2 Inc. licenses this file to you under the Apache License,
#  Version 2.0 (the "License"); you may not use this file except
#  in compliance with the License.
#  You may obtain a copy of the License at
#
#  http:www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing,
#  software distributed under the License is distributed on an
#  "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
#  KIND, either express or implied.  See the License for the
#  specific language governing permissions and limitations
#  under the License.

PROJECT_ROOT := $(realpath $(dir $(abspath $(lastword $(MAKEFILE_LIST)))))
GIT_REVISION := $(shell git rev-parse --verify HEAD)
CELLERY_ORG ?= wso2cellery
CELLERY_VERSION ?= latest

SAMPLE := hello-world
COMPOSITE_FILE := hello-world-composite

all: cellery-build

.PHONY: cellery-build
cellery-build:
	cellery build $(COMPOSITE_FILE).bal $(CELLERY_ORG)/$(COMPOSITE_FILE):$(CELLERY_VERSION); \

.PHONY: cellery-push
cellery-push:
	cellery push $(if $(CELLERY_REGISTRY),$(CELLERY_REGISTRY)/)$(CELLERY_ORG)/$(COMPOSITE_FILE):$(CELLERY_VERSION)  -u $(CELLERY_USER) -p $(CELLERY_USER_PASS); \
