# my-app
python-app
I wrote a dockerfile that takes my python program named "app.py" and creates an image containing the website

"app.py" contains a web application

I created a private repository in Amazon ECR (Elastic Container Registry) and uploaded the image I created

I built a helm "app" which contains deployment that uses imagePullSecrets That pulls it from my personal Amazon account

For it to be possible To pull the image from the private repository I created an aws token

Because each token has a validity of 12 hours and I defined in the deployment imagePullPolicy: Always

To solve the problem I built a CronJob "aws-token.yaml" that is scheduled to run every 10 hours which deletes the old key and 

prepares a new one with the same name

For the documentation in git I uploaded the file "aws-token.yaml"

For So that I will not upload the original file with the personal details

