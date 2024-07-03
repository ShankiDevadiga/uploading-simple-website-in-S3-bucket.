# uploading-simple-website-in-S3-bucket.

This project contains a simple static website consisting of an HTML file and a CSS file. The website is designed to be hosted on an AWS S3 bucket.

## Files

- `index.html`: The main HTML file for the website.
- `styles.css`: The CSS file for styling the website.

## How to Deploy on AWS S3

### Step 1: Create an S3 Bucket

1. Go to the S3 service in the AWS Management Console.
2. Click on "Create bucket".
3. Provide a unique bucket name and select the region.
4. Uncheck "Block all public access" (you need to allow public access for a static website).
5. Click "Create bucket".

### Step 2: Upload the Files

1. Click on your newly created bucket.
2. Click on the "Upload" button.
3. Upload the `index.html` and `styles.css` files.

### Step 3: Configure the Bucket as a Static Website

1. Go to the "Properties" tab.
2. Scroll down to the "Static website hosting" section.
3. Click on "Edit".
4. Select "Enable".
5. For the "Index document", enter `index.html`.
6. Click "Save changes".

### Step 4: Set Bucket Policy to Allow Public Access

1. Go to the "Permissions" tab.
2. Scroll down to the "Bucket policy" section.
3. Click on "Edit".
4. Add the following policy to allow public read access:
    ```json
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "PublicReadGetObject",
                "Effect": "Allow",
                "Principal": "*",
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::your-bucket-name/*"
            }
        ]
    }
    ```
5. Replace `your-bucket-name` with the name of your bucket.
6. Click "Save changes".

### Step 5: Access Your Website

1. Go back to the "Properties" tab.
2. Scroll down to the "Static website hosting" section.
3. Copy the "Endpoint" URL.
4. Open the URL in your browser to see your static website.

## License

This project is licensed under the MIT License.

---

This simple static website is a great starting point for deploying web projects on AWS S3. Feel free to customize and expand upon it as needed.
