# Cloudflare Worker as CORS Proxy

A lightweight and efficient CORS proxy implemented as a Cloudflare Worker. This proxy allows you to bypass CORS restrictions by proxying requests through Cloudflare's global network.

## Features

- Handles all HTTP methods (GET, POST, PUT, DELETE, etc.)
- Supports CORS preflight requests
- Removes problematic headers automatically
- Error handling with informative messages
- URL sanitization and validation

## Quick Start

1. Go to Cloudflare Workers
2. Click "Create Worker"
3. Delete all template code
4. Copy and paste the code from the "cf-worker" file in the repo
5. Deploy

## Usage

Once deployed, you can use the proxy by prepending your Worker's URL to the target URL:
https://your-worker-name.your-account.workers.dev/https://api.example.com/data

Original request that might fail due to CORS
fetch('https://api.example.com/data')

Using the CORS proxy
fetch('https://your-worker-name.your-account.workers.dev/https://api.example.com/data')

## Notes

The proxy adds CORS headers to allow requests from any origin (*)
Maximum request size and timeout limits apply according to Cloudflare Workers' free plan limits
For production use, consider adding rate limiting and security measures
