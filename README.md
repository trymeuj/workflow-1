# PDF Uploader for n8n Webhook

This project is a simple PDF uploader web application built with [Next.js](https://nextjs.org) and React. It allows users to upload a PDF file, which is then sent to an n8n webhook for further processing (such as extracting data, converting to a spreadsheet, etc.). After uploading, the user is notified that they will receive a link to the processed spreadsheet via email.

## Features
- Drag-and-drop or click to select a PDF file
- Only PDF files are accepted
- Upload progress indicator and disabled button during upload
- Sends the PDF to a configurable n8n webhook endpoint
- User is notified of success or error

## How It Works
1. **File Selection:** Users can drag and drop a PDF file or click to select one. Only PDF files are accepted.
2. **File Upload:** When the user submits the form, the selected PDF is sent as a POST request to a specified n8n webhook endpoint using the Fetch API.
3. **User Feedback:** The UI shows upload progress and disables the upload button while uploading. After a successful upload, the user is alerted that the file was sent and to expect an email with the results.
4. **Error Handling:** If the upload fails, the user is shown an error message.

## How to Change the Webhook Endpoint
To change the n8n webhook URL (for example, if you move your workflow or use a different n8n instance):

1. Open `src/app/page.tsx` in your code editor.
2. Find the line:
   ```js
   const response = await fetch('https://husainn8n.app.n8n.cloud/webhook/upload-invoice', {
   ```
3. Replace the URL with your new webhook endpoint.
4. Save the file. The app will now send uploaded PDFs to the new endpoint.

## Getting Started

First, install dependencies and run the development server:

```bash
npm install
npm run dev
# or
yarn install
yarn dev
# or
pnpm install
pnpm dev
# or
bun install
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Customization
- You can edit the UI or logic by modifying `src/app/page.tsx`.
- The page auto-updates as you edit the file.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out the [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
