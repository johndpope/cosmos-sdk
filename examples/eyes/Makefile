COMMIT_HASH := $(shell git rev-parse --short HEAD)
LINKER_FLAGS:="-X github.com/cosmos/cosmos-sdk/client/commands.CommitHash=${COMMIT_HASH}"
NOVENDOR := $(shell glide novendor)

install:
	@go install -ldflags $(LINKER_FLAGS) ./cmd/...

test: test_unit test_cli

test_unit:
	@go test $(NOVENDOR)

test_cli:
	./tests/cli/eyes.sh

.PHONY: install test test_unit test_cli
