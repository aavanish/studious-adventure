# File Structure in Linx 
<img width="1080" height="1350" alt="image" src="https://github.com/user-attachments/assets/2891994c-7789-4bdf-b3ce-42067e7aae05" />

# File Structure Explainantion
<img width="1656" height="907" alt="Screenshot 2026-06-28 204532" src="https://github.com/user-attachments/assets/8aeb1135-7314-4922-9faf-a94a6e1a5ab5" />

# Lets discuss /var/log
## Stores Sytem and application logs.
> **Application-specific logs:** For example, logs from the Apache web server are found in /var/log/apache2/, and logs from MySQL are in /var/log/mysql/.

> **Mail server logs:** These are located in /var/log/mail/.

> **User activity logs:** Such as login/logout records and command history, are stored in the /var/log/ directory or its subdirectories like /var/log/auth.log.
These logs are essential for monitoring system health, troubleshooting issues, and maintaining security. They are organized into subdirectories based on their respective categories or sources, making it easier for system administrators to access and manage them.
