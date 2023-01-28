# AWS Key Rotation Script

A script that rotates access keys for a specific IAM user on a regular basis, in order to improve security and compliance.

# Getting Started

This script is designed to be run as an AWS Lambda function. It uses boto3 library to interact with the AWS IAM service.

# Prerequisites

* An AWS account
* IAM user with permissions to create and manage access keys
* Python 3.8


# Installing
* Create an IAM policy that grants permissions for interacting with access keys using the JSON policy provided in the script.
* Create a Lambda function and attach the previously created IAM policy to the Lambda role.
* Add this script to the Lambda function as the handler.
* In the script, replace 'xxxxx' with the name of the IAM user whose access keys you want to rotate.
* Configure a trigger for the Lambda function (e.g. set it to run on a schedule).

# Usage

* The script uses the lambda_handler function as the entry point.
* The lambda_handler function lists the access keys for the specified user, then disables and deletes the keys that are older than 90 days, and creates new ones.
* The list_access_key function lists the access keys for a user, filtering by age and status.
* The time_diff function calculates the difference between the current time and the time a key was created.
* The create_key function creates a new access key for a user.
* The disable_key function disables an existing access key for a user.
* The delete_key function deletes an existing access key for a user.

# Contributing

Feel free to contribute to this project by submitting pull requests with new features or bug fixes.

# Authors

Aatir Siddiqui

# License

This project is licensed under the MIT License - see the LICENSE.md file for details.

# Acknowledgments

AWS IAM service and boto3 library
Disclaimer
Please be sure to thoroughly test and review this script before deploying it to a production environment. This script is provided as is with no guarantee or warranty.
