# Bouncer Email Verification Server

## Overview

Bouncer Email Verification is a robust and efficient email verification server designed for real-time validation of email addresses. This server is ideal for both CEOs and developers looking for a reliable tool to ensure the accuracy and deliverability of their email lists.

## Features

- **Real-Time Email Verification**: Bouncer's server checks the syntax and domain of an email address and connects with underlying SMTP servers to verify its deliverability.
- **Fast and Reliable**: The server provides results within a chosen timeout, with a default of 10 seconds and a maximum of 30 seconds.
- **Detailed Status Reporting**: Each email address is classified as 'deliverable', 'undeliverable', 'risky', or 'unknown', providing a comprehensive overview of its status.
- **Error Handling**: Utilizes standard HTTP error codes to indicate the success or failure of requests.

## Statuses Explained

- **Deliverable**: The email address is confirmed by the recipient's email provider and is safe to send.
- **Risky**: The email address might result in a bounce or low engagement due to factors like full mailboxes or being a disposable email.
- **Undeliverable**: The email address is syntactically incorrect or does not exist.
- **Unknown**: The server couldn't receive a response from the email provider.

## Reasons for Status

- **Deliverable**: `accepted_email` - The email address was accepted.
- **Risky**: 
  - `low_deliverability` - Deliverability cannot be guaranteed.
  - `low_quality` - The address has quality issues, often due to being disposable.
- **Undeliverable**:
  - `invalid_email` - Invalid syntax.
  - `invalid_domain` - The domain does not exist or lacks valid DNS records.
  - `rejected_email` - Rejected by the SMTP server.
  - `no_connect` - Unable to connect to the SMTP server.
- **Unknown**:
  - `dns_error` - DNS resolution failed or misconfigured.
  - `unavailable_smtp` - SMTP server unavailable.
  - `unknown` - An unexpected error occurred.

## Tool Usage

### Verify Email

- **Function Name**: `verify_email`
- **Description**: Verifies a single email address in a real-time, synchronous manner.
- **Parameters**:
  - `email` (String): The email address to verify.
  - `timeout` (Number, optional): The timeout for verification, with a maximum of 30 seconds and a default of 10 seconds.

The Bouncer Email Verification server provides a powerful tool for maintaining clean and efficient email lists, ensuring high deliverability and engagement rates.