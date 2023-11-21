HELM_CHART_VER=7.0.8
NAMESPACE="grafana"

install: ## installs grafana helm chart
	helm upgrade --install grafana grafana/grafana --version $(HELM_CHART_VER) -n $(NAMESPACE) -f values.yaml

uninstall: ## uninstalls grafana helm chart
	helm uninstall grafana -n $(NAMESPACE)

env: ## list environment variables
	@echo HELM_CHART_VER=$(HELM_CHART_VER)
	@echo NAMESPACE=$(NAMESPACE)

.PHONY: help

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

.DEFAULT_GOAL := help
