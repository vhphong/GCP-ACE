# Billing
- Most service on the cloud cost money
- There is a free tier for 90 days that comes with a $300 credit
- Billing Accounts pay for services
    - Self Serve accounts
        - Billing is charged to a credit card or debited from an accout
    - Invoice
        - Enterprise customers might have more custom plans
    - Cloud Billing
        - You can find how much projects cost, future costs, and current monthly spending. You can break it down per project 
- Billing Roles
    - Billing Account creator  
        - Make Billing accounts 
        - Use this role for initial billing setup or to allow creation of additional billing accounts. Users must have this role to sign up for Google Cloud with a credit card using their corporate identity.
    - Billing Account Administrator
        - Manage accounts 
        - This role is an owner role for a billing account. Use it to manage payment instruments, configure billing exports, view cost information, link and unlink projects and manage other user roles on the billing account.
    - Billing Account User 
    - This role has very restricted permissions, so you can grant it broadly, typically in combination with Project Creator. These two roles allow a user to create new projects linked to the billing account on which the role is granted.
        - Link accounts to projects
    - Billing Account Viewer
        - View but not edit billing accounts
        - Billing Account Viewer access would usually be granted to finance teams, it provides access to spend information, but does not confer the right to link or unlink projects or otherwise manage the properties of the billing account.
    - Project Billing Manager
        - link/unlink the project to/from a billing account 
        - This role allows a user to attach the project to the billing account, but does not grant any rights over resources. Project Owners can use this role to allow someone else to manage the billing for the project without granting them resource access.
- Exporting Billing Data
    - BiqQuery
        - Data becomes a billing set
    - GCS 
        - Data a file in JSON or CSV format
        

    