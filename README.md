# file-test-bed

Simple static page to test downloads/uploads

## 🎯 Purpose

This repository contains a static HTML + JavaScript page designed to trigger simultaneous downloads of two encrypted ZIP files. It's perfect for testing Chrome extensions that monitor or intercept file downloads.

## 🚀 Usage

### Access the Page

The page is hosted on GitHub Pages at: `https://jonnylin13.github.io/file-test-bed/`

Or open `index.html` locally in your browser.

### Trigger Downloads

Simply click the "Download Both Files" button to initiate simultaneous downloads of two test files:
- `encrypted-file-1.zip`
- `encrypted-file-2.zip`

## 🔧 Customizing the Data URLs

The page currently uses placeholder data URLs for the ZIP files. To use actual encrypted ZIP files:

1. Open `index.html` in a text editor
2. Locate the `FILE_DATA_URLS` object in the JavaScript section
3. Replace the `dataUrl` values with your actual data URLs:

```javascript
const FILE_DATA_URLS = {
    file1: {
        name: 'encrypted-file-1.zip',
        dataUrl: 'data:application/zip;base64,YOUR_BASE64_ENCODED_ZIP_HERE'
    },
    file2: {
        name: 'encrypted-file-2.zip',
        dataUrl: 'data:application/zip;base64,YOUR_BASE64_ENCODED_ZIP_HERE'
    }
};
```

### How to Generate Data URLs

To convert your encrypted ZIP files to data URLs:

```bash
# On Linux/Mac
base64 -i your-encrypted-file.zip | tr -d '\n' > encoded.txt
# Then prepend: data:application/zip;base64,

# Or use an online tool like: https://www.base64-image.de/
```

Or use this JavaScript snippet in the browser console:

```javascript
// Using File API
const file = // your File object
const reader = new FileReader();
reader.onload = function(e) {
    console.log(e.target.result); // This is your data URL
};
reader.readAsDataURL(file);
```

## 🧪 Testing Chrome Extensions

This page is ideal for testing Chrome extensions that:
- Monitor download events
- Intercept file downloads
- Analyze file metadata
- Test simultaneous download handling
- Validate encrypted file detection

## 📋 Features

- ✅ Clean, modern UI
- ✅ Simultaneous download triggering
- ✅ Data URL-based downloads (no server required)
- ✅ Ready for GitHub Pages
- ✅ Mobile-responsive design
- ✅ Status feedback for users

## 🛠️ Local Development

No build process required! Simply open `index.html` in your browser.

## 📄 License

MIT
