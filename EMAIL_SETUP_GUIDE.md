# EmailJS Setup Guide

## Overview
I've implemented an advanced email solution using EmailJS that will automatically send emails to ana.s@mr-ins.co.il without any user interaction. Here's how to set it up:

## Step 1: Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## Step 2: Add Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the setup instructions to connect your email account
5. Note down the **Service ID** (you'll need this)

## Step 3: Create Email Template
1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template structure:

**Template Name:** `new_lead_notification`

**Subject:** `{{subject}}`

**Content:**
```
{{message}}

---
פרטי ליצירת קשר:
שם: {{customer_name}}
אימייל: {{customer_email}}
טלפון: {{customer_phone}}
סניף: {{customer_branch}}
מקור: {{source_id}}
זמן הגשה: {{submission_time}}
```

4. Save the template and note down the **Template ID**

## Step 4: Get Your Public Key
1. Go to "Account" → "General"
2. Find your **Public Key**

## Step 5: Update the HTML File
Replace these placeholders in the `index.html` file:

1. Line 13: Replace `"YOUR_PUBLIC_KEY"` with your actual public key
2. Line 54: Replace `'YOUR_SERVICE_ID'` with your service ID  
3. Line 54: Replace `'YOUR_TEMPLATE_ID'` with your template ID

## Example Configuration:
```javascript
// Replace line 13:
emailjs.init("user_1234567890abcdef"); // Your actual public key

// Replace line 54:
emailjs.send('service_gmail123', 'template_abc456', templateParams)
```

## Step 6: Test the Setup
1. Open your webpage
2. Fill out the form completely
3. Submit the form
4. Check ana.s@mr-ins.co.il for the email

## Features Included:
- ✅ Automatic email sending (no user action required)
- ✅ Professional email formatting in Hebrew
- ✅ All form data included in email
- ✅ Fallback to mailto link if EmailJS fails
- ✅ Loading states and error handling
- ✅ Responsive design maintained

## Free Tier Limits:
- EmailJS free tier allows 200 emails per month
- If you need more, consider upgrading to a paid plan

## Troubleshooting:
- If emails aren't sending, check the browser console for errors
- Make sure all IDs are correctly replaced
- Verify your email service is properly connected in EmailJS dashboard
- Test with a simple template first

## Security Note:
The public key is safe to include in frontend code - it's designed for client-side use and has limited permissions.
