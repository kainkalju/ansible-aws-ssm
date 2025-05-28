# Ansible Example Project

This project contains Ansible playbooks and roles for managing AWS resources, specifically for installing the `httpd` web server on EC2 instances and creating an S3 bucket required for AWS SSM connections.

## Project Structure

```
ansible-aws-project
├── playbooks
│   ├── install_httpd.yml       # Playbook to install httpd on EC2 instances
│   └── create_s3_bucket.yml    # Playbook to create an S3 bucket
├── inventory
│   └── hosts.ini               # Inventory file for EC2 instances
├── roles
│   ├── bucket
│   │   ├── tasks
│   │   │   └── main.yml        # Main tasks for the bucket role
│   │   └── vars
│   │       └── main.yml        # Variables for the bucket role
│   └── httpd
│       └── tasks
│           └── main.yml        # Main tasks for the httpd role
├── requirements.yml            # Required Ansible collections and roles
├── playbook.yml                # Example or main playbook entry point
└── README.md                   # Project documentation
```

## Setup Instructions

1. **Install Ansible**: Ensure you have Ansible installed on your local machine. You can install it using pip:

   ```
   pip install ansible
   ```

2. **Install Required Collections**: Use the `requirements.yml` file to install any necessary Ansible collections or roles:

   ```
   ansible-galaxy collection install -r requirements.yml
   ```

3. **Configure AWS Credentials**: Make sure your AWS credentials are configured properly. You can set them in `~/.aws/credentials` or export them as environment variables.

4. **Inventory Configuration**: Update the `inventory/hosts.ini` file with your EC2 instance details.

## Usage Examples

- To install `httpd` on your EC2 instances, run the following command:

  ```
  ansible-playbook -i inventory/hosts.ini playbooks/install_httpd.yml
  ```

- To create the S3 bucket, execute:

  ```
  ansible-playbook -i inventory/hosts.ini playbooks/create_s3_bucket.yml
  ```

## Contributing

Feel free to submit issues or pull requests if you have suggestions or improvements for this project.