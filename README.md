Sure! Here's a detailed and colorful README file in markdown format, with emojis and rich content to make it more engaging for users.

```markdown
# Shopify Product Creation Automation Script 📦🛒

Welcome to the **Shopify Product Creation Automation** script! 🚀 This script automates the process of creating and managing products in a **Shopify store** using data extracted from **PDF files**. It also integrates with **Google Drive** to upload PDF files and attach them to the created products, making the entire workflow smooth and efficient. 🎯

## Overview 🌟

This script performs the following main tasks:

- **Reads configuration settings** from a JSON file.
- **Processes PDF files** to create products in Shopify.
- **Attaches images** to the created products.
- **Uploads PDF files to Google Drive** and links them to the created products.
- Provides options to **activate or delete** products.
- **Sends a CSV file** to a webhook and renames it after processing.

## Prerequisites 🔧

Before running the script, ensure you have the following:

### Required Software:
- **Python 3.x** installed on your system. 🐍

### Required Python Packages:
Install the necessary dependencies by running:

```bash
pip install -r requirements.txt
```

The required Python packages include:
- `requests`
- `pandas`
- `google-auth`
- `google-auth-oauthlib`
- `google-auth-httplib2`
- `google-api-python-client`

### Credentials:
- **Shopify Store**: You need the **store URL** and an **API access token**.
- **Google Drive**: You need a **Google service account JSON file** with the necessary permissions to upload files to Google Drive.

### Configuration File:
The script uses a `config.json` file located in the source folder for product creation configuration.

## Configuration 🛠️

1. **Shopify Store**: 
   - **Store URL**: `your-store.myshopify.com`
   - **Access Token**: `shpat_abc12345def67890ghijklmnopqrst`

2. **Google Drive**:
   - **Credentials Path**: `/path/to/google/credentials.json`

3. **Configuration File**: 
   - Ensure your `config.json` file is in place and contains the required data for product creation.

## Script Usage 📋

### Command Line Arguments ⚙️

The script accepts the following command-line arguments:

- `--source-folder`: Path to the folder containing PDFs and images (default: `2024Q3`).
- `--store-url`: Your Shopify store URL (default: `project-digital-shop.myshopify.com`).
- `--access-token`: Shopify access token (default: `test - `).
- `--credentials-path`: Path to your Google Drive credentials JSON (default: `python-444308-6e5be7255eac.json`).

### Running the Script 🏃‍♂️

1. **Prepare the Source Folder**: 
   - Ensure the source folder contains the PDF files, images, and the `config.json` file.

2. **Run the Script**: 
   Execute the script with the following command:

```bash
python main.py --source-folder /path/to/source/folder --store-url your-shopify-store.myshopify.com --access-token your-access-token --credentials-path /path/to/credentials.json
```

3. **User Inputs**: 
   The script will prompt you to enter:
   - **Year**: Enter the year for the product batch.
   - **Quarter**: Enter the quarter of the year.
   - **Number of Markets**: Choose the number of markets to process.

4. **Processing**: 
   - The script processes the PDFs, creates products in Shopify, attaches images, uploads PDFs to Google Drive, and updates the products with the file URLs.

5. **Final Action**: 
   After processing, the script will ask you to choose whether to **activate** or **delete** the created products in Shopify.

### Example Usage 🎬

```bash
python main.py --source-folder ./2024Q3 --store-url project-digital-shop.myshopify.com --access-token shpat_xyz12345 --credentials-path ./google-credentials.json
```

## Functions 🔍

### `read_config(config_path: str)`
Reads the configuration file and returns the configuration data.

### `create_product(store_url: str, product_data: dict, access_token: str, year: str, quarter: str, config: dict)`
Creates a product in Shopify using the provided data.

### `attach_image_to_product(store_url: str, product_id: int, image_path: str, access_token: str)`
Attaches an image to a Shopify product.

### `clean_string(input_string: str) -> str`
Cleans a string by converting to lowercase, removing file extensions, and replacing special characters with spaces.

### `generate_csv_header(csv_file_path)`
Generates the CSV file header if it doesn't exist.

### `update_csv_with_drive_url(csv_file_path: str, product_id: str, drive_url: str)`
Updates the CSV file with the Google Drive URL for a specific product.

### `insert_data_to_csv(csv_file_path, product_id, pdf_path)`
Inserts product data into the CSV file after the product is created.

### `setup_google_drive(credentials_path: str)`
Sets up the Google Drive API client.

### `upload_to_drive(service, file_path: str, folder_id: Optional[str] = None) -> str`
Uploads a file to Google Drive and returns its shareable link.

### `update_product_with_file(store_url: str, product_id: int, file_url: str, access_token: str)`
Updates a Shopify product with a digital download URL.

### `process_uploaded_files(csv_path: str, store_url: str, access_token: str, credentials_path: str)`
Processes uploaded files from CSV and uploads them to Google Drive.

### `process_pdfs(source_folder: str, store_url: str, access_token: str, config: dict, year: str, quarter: str, markets_to_process: Optional[int] = None)`
Processes PDFs and creates products in Shopify.

### `activate_products(store_url: str, access_token: str, csv_file_path: str)`
Activates products in Shopify.

### `delete_products(store_url: str, access_token: str)`
Deletes products from Shopify.

### `send_csv_to_webhook(csv_file_path: str, webhook_url: str)`
Sends the CSV file to a specified webhook.

### `send_file_and_rename(csv_file_path)`
Sends and renames the file, returning the new file path.

### `parse_args()`
Parses the command-line arguments.

### `main()`
The main function that executes the script.

## Logging 📜

The script uses enhanced logging to log important events and errors. The log file is saved as `CreateProducts.log` in the project directory. You can refer to it for debugging and tracking the script's execution.

## License 📑

This project is licensed under the **MIT License**.

---

We hope this script makes your Shopify product creation process smoother and more efficient! 🛠️✨

Feel free to open an issue if you encounter any bugs or need help. Happy coding! 😄
```

