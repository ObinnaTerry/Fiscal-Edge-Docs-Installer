# Changelog

## [3.0.0] - 2025-03-09

### Added
- **Pastel POS Integerated Support**  
  The application now includes seamless integration with Sage Pastel for both Access and SQL Server databases. This enhancement allows invoices raised in Pastel POS to be fiscalized directly from the POS without waiting for synchronization with the backend. Additionally, Pastel POS templates can now be updated to include fiscal details without requiring invoices to be reprinted from the server.


### Enhancements
- **SQL Script Performance Optimization**  
  General performance optimizations.


## [2.1.2] - 2025-02-01

### Added
- **Mixed Mode Support**  
  The application now supports mixed-mode usage, which is particularly useful in scenarios where both Pastel and Sage 200 are running on the same server. 

- **Support for the new ZRA Invoice Number Format**  
  The application and scripts have been updated to comply with the latest ZRA invoice number format recommendations.

### Enhancements
- **SQL Script Performance Optimization**  
  The SQL scripts have been optimized to improve overall query performance, especially for databases with large datasets.

### Fixed
- **Missing Customer TPIN** 
   This release addresses an issue that occasionally caused missing customer TPINs on transmitted invoices.

## [2.0.0] - 2024-10-29

### Added
- **Job Card Support**  
  The application can support Job Card invoice fiscalization. This feature can be enabled by setting the `HasJobCard` parameter in the configuration file to `true`.

## [1.6.0] - 2024-10-05

### Added
- **Base64 QR Code Image Support**  
  The application can now convert the QR Code URL to a base64 image, simplifying the process of rendering QR codes on invoices without the need for additional conversions. This feature can be enabled by setting the `Base64Image` parameter in the configuration file to `true`.

- **Line Item Retrieval Delay**  
  Added a configurable delay between the retrieval of invoice headers and line items. This addresses an issue specific to Palladium users, where a timing mismatch can cause a "No Items Found for this Invoice" error. Use the `PalladiumDelay` parameter in the configuration file to configure this delay in seconds. For non-Palladium ERP systems, set this field to `0` to avoid unnecessary delays in invoice processing times.

### Enhancements
- **Enhanced Handling of Connection Errors**  
  Improved error handling for invoices that fail to fiscalize due to network connectivity issues. Instead of entering an error state and requiring manual intervention, these invoices will now remain in a "non-processed" state, allowing the application to automatically retry fiscalization during subsequent attempts.

## [1.5.2] - 2024-10-03
### Enhancements
- **Increased Decimal Precision for Unit Prices**  
  Updated the unit price precision from 4 to 8 decimal places to comply with the latest ZRA specifications. This update addresses issues that previously caused invoices to fail with an 'Invalid Total Amount' error.

- **Improved Sage Evolution SQL Script**  
  Enhanced the SQL script to handle multiple partial invoices generated from a single sales order, ensuring accurate invoicing and improved compatibility with Sage Evolution.

## [1.5.0] - 2024-09-05
### Added
- Added support for managing multiple inventory branches.
This feature allows different branches, sharing the same database, to be registered as separate branches with the ZRA (Zambia Revenue Authority).
Each branch must have its own distinct warehouse to support this functionality.

### Changed


### Fixed