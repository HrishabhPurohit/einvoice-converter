# E-Invoice CSV to JSON Converter

A cross-platform desktop application that converts E-Invoice CSV files to JSON format (V4 specification).

## Features

- **Simple & Intuitive**: Drag & drop CSV files or browse to select
- **Auto-Mapping**: Automatically maps CSV columns to JSON fields
- **Cross-Platform**: Works on Windows, macOS, and Linux
- **E-Invoice V4 Compliant**: Generates JSON matching E-Invoice V4 specification
- **Batch Processing**: Handles multiple invoices in a single CSV file

## Installation

### Prerequisites
- Node.js 16+ and npm

### Setup
```bash
cd einvoice-converter
npm install
```

## Usage

### Development Mode
```bash
npm start
```

### Build Distributables

**All platforms:**
```bash
npm run dist
```

**Platform-specific:**
```bash
npm run dist:mac    # macOS (DMG)
npm run dist:win    # Windows (NSIS installer)
npm run dist:linux  # Linux (AppImage)
```

Built files will be in the `dist/` directory.

## How to Use

1. **Launch** the application
2. **Upload** your E-Invoice CSV file by:
   - Dragging and dropping it into the upload area, or
   - Clicking "Browse Files" to select it
3. **Convert** by clicking the "Convert to JSON" button
4. **Download** automatically starts - JSON file saved with `_converted.json` suffix

## CSV Format Requirements

The CSV file should contain the following columns:
- Document Number, Document Date, Document Type
- Buyer GSTIN, Buyer Legal Name, Buyer details
- Supply Type Code, GST details
- Item details: Product Description, HSN Code, Quantity, Unit, Prices
- Tax details: SGST, CGST, IGST amounts and rates

## Sample Files

Sample files are available in the project root:
- `EINVOICE.CSV` - Sample input CSV
- `E-INVOICE_V4_JSON.json` - Sample output JSON

## Output Format

The tool generates JSON in E-Invoice V4 format with:
- Version 1.1
- Transaction Details (TranDtls)
- Document Details (DocDtls)
- Seller Details (SellerDtls) - Fixed for CHHATTISGARH MEDICOSE
- Buyer Details (BuyerDtls)
- Value Details (ValDtls)
- Item List (ItemList) with all line items

## Technical Stack

- **Electron** - Cross-platform desktop framework
- **React** - UI framework
- **Papa Parse** - CSV parsing library
- **Electron Builder** - Application packaging

## License

MIT

## Support

For issues or questions, please contact the development team.
