# {{cookiecutter.data_product_1_name}} - Data Product Description

## Overview
This document describes the {{cookiecutter.data_product_1_name}} data product.

## Purpose
[Describe the purpose and business value of this data product]

## Data Product Details

### Data Sources
- **Source 1**: [Describe the data source]
  - **Type**: [Database/API/File/Stream]
  - **Format**: [JSON/CSV/XML/etc.]
  - **Frequency**: [Real-time/Daily/Weekly/etc.]
  - **Volume**: [Estimated data volume]

- **Source 2**: [Describe the data source]
  - **Type**: [Database/API/File/Stream]
  - **Format**: [JSON/CSV/XML/etc.]
  - **Frequency**: [Real-time/Daily/Weekly/etc.]
  - **Volume**: [Estimated data volume]

### Data Schema
```json
{
  "field1": {
    "type": "string",
    "description": "Description of field1",
    "required": true
  },
  "field2": {
    "type": "number",
    "description": "Description of field2",
    "required": false
  }
}
```

### Data Quality
- **Completeness**: [Describe completeness requirements]
- **Accuracy**: [Describe accuracy requirements]
- **Consistency**: [Describe consistency requirements]
- **Timeliness**: [Describe timeliness requirements]

## Data Transformations

### Transformation 1: [Transformation Name]
- **Input**: [Describe input data]
- **Process**: [Describe transformation process]
- **Output**: [Describe output data]

### Transformation 2: [Transformation Name]
- **Input**: [Describe input data]
- **Process**: [Describe transformation process]
- **Output**: [Describe output data]

## Data Consumers

### Consumer 1: [Consumer Name]
- **Type**: [Dashboard/Report/API/Application]
- **Usage**: [Describe how data is used]
- **Frequency**: [How often data is consumed]

### Consumer 2: [Consumer Name]
- **Type**: [Dashboard/Report/API/Application]
- **Usage**: [Describe how data is used]
- **Frequency**: [How often data is consumed]

## Data Governance

### Data Ownership
- **Data Owner**: [Name and contact information]
- **Data Steward**: [Name and contact information]
- **Technical Owner**: [Name and contact information]

### Data Classification
- **Classification Level**: [Public/Internal/Confidential/Restricted]
- **Retention Period**: [Specify retention period]
- **Privacy Requirements**: [Describe privacy requirements]

### Data Lineage
[Describe the data lineage from source to consumer]

## Service Level Agreements (SLAs)

### Availability
- **Target**: [e.g., 99.9% uptime]
- **Measurement**: [How availability is measured]

### Performance
- **Latency**: [Target latency requirements]
- **Throughput**: [Target throughput requirements]

### Data Freshness
- **Target**: [e.g., Data available within 15 minutes of source update]
- **Measurement**: [How freshness is measured]

## Monitoring and Alerting

### Key Metrics
- **Metric 1**: [Describe metric and threshold]
- **Metric 2**: [Describe metric and threshold]

### Alerts
- **Alert 1**: [Describe alert condition and response]
- **Alert 2**: [Describe alert condition and response]

## Documentation and Support

### Documentation
- **Technical Documentation**: [Link to technical docs]
- **User Guide**: [Link to user guide]
- **API Documentation**: [Link to API docs if applicable]

### Support
- **Support Team**: [Contact information]
- **Support Hours**: [Available support hours]
- **Escalation Process**: [Describe escalation process]

## Version History
| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | [Date] | Initial version | [Author] |

## Related Data Products
- [List related data products and their relationships]