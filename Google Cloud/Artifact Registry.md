# Artifact Registry Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Pushing an Image to Artifact Registry

Build Docker image
```Bash
docker build -t <IMAGE_NAME>[:<IMAGE_TAG>]
```

Install missing components
```Bash
sudo apt -y install install kubectl docker-credential-gcr
```

Push Docker image to GCR
```Bash
docker tag <IMAGE_NAME>[:<IMAGE_TAG>] gcr.io/<PROJECT_ID>/<IMAGE_NAME>
docker push gcr.io/<PROJECT_ID>/<IMAGE_NAME>
```
