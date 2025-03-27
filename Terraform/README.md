# Install Terraform

1. Download terraform the latest version from [here](https://www.terraform.io/downloads)

2. Setup environment variable  
   - Click on Start → Search "edit the environment variables" and click on it  
   - Under the **Advanced** tab, choose **Environment Variables**  
   - Under **System Variables**, select **Path** and add the Terraform location in the path variable  
   - Click **New** and add the path:  

     ```
     C:\Program Files\terraform_1.3.7
     ```

3. Run the below command to validate the Terraform version:

   ```sh
   terraform -version

