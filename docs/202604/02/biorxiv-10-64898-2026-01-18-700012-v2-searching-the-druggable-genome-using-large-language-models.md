---
title: Searching the Druggable Genome using Large Language Models
authors: "Schimmelpfennig, L. E., Cannon, M., Cody, Q., McMichael, J., Coffman, A., Kiwala, S., Krysiak, K. J., Wagner, A. H., Griffith, M., Griffith, O. L."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.18.700012v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型用于搜索可成药基因组和药物-基因相互作用
tldr: 该研究开发了MCP服务器，使大语言模型能够通过自然语言查询药物-基因相互作用数据库。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700012-v2/fig-001.webp\", \"caption\": \"Figure 1. Joint use of the CIViC MCP and DGIdb MCP servers for drug candidate selection 201 with Claude. A user asks, “What genes can cause resistance to Ibrutinib in Chronic Lymphocytic 202 Leukemia, and what alternative drugs can target them?” The LLM: (1) extracts the users intent 203\", \"page\": 10, \"index\": 1, \"width\": 1052, \"height\": 1183}]"
motivation: 大语言模型用于搜索可成药基因组和药物-基因相互作用。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
The druggable genome encompasses the genes that are known or predicted to interact with drugs. The Drug-Gene Interaction Database (DGIdb) provides an integrated resource for discovering and contextualizing these interactions, supporting a broad range of research and clinical applications. DGIdb is currently accessed through structured web interfaces and API calls, requiring users to translate natural-language questions into database-specific query patterns. To allow for the use of DGIdb through natural language, we developed the DGIdb Model Context Protocol (MCP) server, which allows large language models (LLMs) access to up-to-date information through the DGIdb API. We demonstrate that the MCP server greatly enhances an LLM's ability to answer questions requiring accurate, up-to-date biomedical knowledge drawn from structured external resources. Availability and implementation: The DGIdb MCP server is detailed at https://github.com/griffithlab/dgidb-mcp-server and includes instructions for accessing the server through the Claude desktop app.