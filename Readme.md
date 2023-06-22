# json-file-importer

## Description

This is a simple example of how to import a JSON file from a HTML file with simple JavaScript code.


## Typical errors for this use case

Here are some problems you can encounter when trying to find a solution to import JSON files into a HTML file.

### Access to fetch at 'file:///<path>/json-file-importer/src/example.json' from origin 'null' has been blocked by CORS policy: Cross origin requests are only supported for protocol schemes: http, data, isolated-app, chrome-extension, chrome, https, chrome-untrusted.

The error you're seeing is due to a security feature in web browsers called the Same-Origin Policy. This policy prevents web pages from making requests to resources on a different domain, port, or protocol than the one that served the page.

Here, you're trying to fetch a file from the local file system using the `file://` protocol, which is not allowed by the Same-Origin Policy. To fix this, you can serve your HTML and JSON files from a local web server instead of opening them directly in the browser.

One way to do this is to use the `http-server` package from npm. Here's how you can install and use it:

1. Install `http-server` globally using npm:

   ```
   npm install -g http-server
   ```

   or using Homebrew (MacOS):

   ```
   brew install http-server
   ```

2. Navigate to the directory containing your HTML and JSON files in the terminal.

3. Start the server by running the following command:

   ```
   http-server
   ```

4. Open your browser and navigate to `http://localhost:8080/index.html` (replace `index.html` with the name of your HTML file).

This should serve your HTML and JSON files from a local web server, which should allow you to fetch the JSON file without encountering the CORS error.

If you want to specify a different port, you can use the `-p` or `--port` option followed by the desired port number. For example, to start the server on port 3000, you can run the following command:

```
http-server -p 3000
```
