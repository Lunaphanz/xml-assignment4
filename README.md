# XML Assignment 4: Hotels Data Processing

## Overview

This project implements XML schema validation and JSON transformation for hotel data, following the structure and validation approach demonstrated in the [Courses.xsd and Courses.xml](https://venus.sod.asu.edu/WSRepository/xml/Courses.xsd) example from ASU's Distributed Software Development course.

## Repository Structure

```
xml-assignment4/
├── Hotels.xsd          # XML Schema Definition for hotels data
├── Hotels.xml           # Valid hotel data conforming to the schema
├── HotelsErrors.xml     # XML file with intentional errors for testing
└── README.md           # This file
```

## Files Description

### Hotels.xsd

The XML Schema Definition file that specifies the structure, data types, and validation rules for hotel data. Key features:

- **Target Namespace**: `https://lunaphanz.github.io/xml-assignment4`
- **Root Element**: `Hotels`
- **Hotel Elements**: Contains multiple hotel entries with the following structure:
  - `Name` (required string element)
  - `Phone` (required string element, can occur multiple times)
  - `Address` (required complex element):
    - `Number` (required string)
    - `Street` (required string)
    - `City` (required string)
    - `State` (required string)
    - `Zip` (required string)
    - `NearestAirport` (required attribute)
  - `Rating` (optional string attribute)

The schema follows W3C XML Schema standards and uses qualified element form and unqualified attribute form, similar to the Courses.xsd example.

### Hotels.xml

Valid XML document containing sample hotel data that conforms to the Hotels.xsd schema. Includes:

- Three sample hotels with complete information
- Multiple phone numbers where applicable
- Address information with nearest airport attribute
- Optional rating attributes

**Namespace**: `https://lunaphanz.github.io/xml-assignment4`

### HotelsErrors.xml

XML document containing intentional validation errors for testing purposes. Includes various error types such as:

- Missing required attributes
- Missing required elements
- Incorrect data types
- Invalid element names
- Schema violations

## Schema Structure

The schema follows the pattern established in the Courses.xsd example:

- Uses `xsd:` prefix for schema elements
- Defines a target namespace
- Uses `elementFormDefault="qualified"` for elements
- Uses `attributeFormDefault="unqualified"` for attributes
- Implements proper complex type definitions
- Validates required vs optional components

## Access URLs

All files are hosted via GitHub Pages and accessible at:

- **Hotels.xsd**: https://lunaphanz.github.io/xml-assignment4/Hotels.xsd
- **Hotels.xml**: https://lunaphanz.github.io/xml-assignment4/Hotels.xml
- **HotelsErrors.xml**: https://lunaphanz.github.io/xml-assignment4/HotelsErrors.xml

## Usage

### Validation

The XML files can be validated against the schema using:

1. **XML Editors**: Most XML editors (VS Code, XMLSpy, oXygen) support XSD validation
2. **Command Line Tools**: `xmllint` or similar XML validation tools
3. **C# Program**: Use the `submission.cs` program for automated validation

### Testing

1. Validate `Hotels.xml` against `Hotels.xsd` - should pass with no errors
2. Validate `HotelsErrors.xml` against `Hotels.xsd` - should report validation errors

## Technical Details

### Namespace Configuration

- **Target Namespace**: `https://lunaphanz.github.io/xml-assignment4`
- **Schema Location**: Specified in XML documents via `xsi:schemaLocation`
- **Default Namespace**: Applied to all elements in the Hotels namespace

### Schema Validation

The schema enforces:
- Required elements: Name, Phone, Address (with all sub-elements)
- Required attributes: NearestAirport on Address element
- Optional attributes: Rating on Hotel element
- Multiple occurrences: Phone elements can appear multiple times

## Reference

This project is based on the structure demonstrated in:
- **[Courses.xsd Example](https://venus.sod.asu.edu/WSRepository/xml/Courses.xsd)**: ASU CSE445 Distributed Software Development course example

## Author

Created for ASU CSE445 Assignment 4.

## License

Educational project for ASU CSE445 course.

---

**Note**: This repository is configured for GitHub Pages to serve the XML and XSD files for remote validation and testing.

