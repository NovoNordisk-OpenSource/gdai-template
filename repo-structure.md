# GD&AI Repositories

This document describes the preferred and recommended structure of any repository supporting platform components, use cases and data products. The Structure of the repository outlined in this document, will be supporting the path to production process as outlined in the [path to production](path-to-production.md) document.
The repository structure provides mandatory artifacts and templates required to accellerated the the path to production.

## Repository Structure

The repository structure is as follows:

```
GD&AI-Repository
├── .github
│   ├── ISSUE_TEMPLATE
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── use_case.md
│   └── workflows
├── /docs
├── /src
│   ├── /main
│   └── /test
├── /tests
│   ├── /unit
│   └── /integration
├── /test-scenarios
│   ├── /unit
│   └── /integration
├── README.md
├── LICENSE
└── .gitignore
```

### .github
