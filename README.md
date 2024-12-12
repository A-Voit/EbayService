# Ebay Image Search API

A C# backend project that uses eBay's Image API to perform reverse image searches. This application is built with **ASP.NET Core Web API** and is designed to allow users to upload an image and retrieve eBay product listings based on visual similarity.

## Features

- Reverse image search using eBay's Image API.
- Upload image files and get matched eBay listings.
- Securely handles API tokens and credentials.

## Prerequisites

- [.NET SDK](https://dotnet.microsoft.com/download)
- [Visual Studio Code](https://code.visualstudio.com/)
- eBay Developer Account ([Sign up here](https://developer.ebay.com/))

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/EbayImageSearch.git
cd EbayImageSearch
```

### 2. Configure eBay API Credentials
- Go to the [eBay Developer Portal](https://developer.ebay.com/) and create an application.
- Obtain your **Client ID** and **Client Secret**.
- Set them as environment variables or add them directly to the `ImageSearchController.cs` file (not recommended for production).

### 3. Install Dependencies
Restore the required NuGet packages:
```bash
dotnet restore
```

### 4. Run the Application
Start the development server:
```bash
dotnet run
```

The API will be available at `http://localhost:5000`.

## Usage

### Endpoint: `/api/ImageSearch/search`

- **Method**: `POST`
- **Content-Type**: `multipart/form-data`
- **Parameters**:
  - `imageFile` (required): An image file to be uploaded.

### Example with cURL:
```bash
curl -X POST "http://localhost:5000/api/ImageSearch/search" \
     -H "Content-Type: multipart/form-data" \
     -F "imageFile=@path/to/image.jpg"
```

### Example Response:
```json
{
  "items": [
    {
      "title": "Product Title",
      "price": "$25.00",
      "image": "https://example.com/image.jpg",
      "url": "https://www.ebay.com/itm/123456789"
    }
  ]
}
```

## Project Structure

- `Controllers/ImageSearchController.cs`: Handles API endpoints and integrates with eBay Image API.
- `Program.cs`: Configures the application and middleware.

## Future Improvements

- Add logging and better error handling.
- Implement token caching to minimize API requests.
- Deploy to a cloud service (e.g., Azure, AWS, or Heroku).
- Build a frontend for easier interaction.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

