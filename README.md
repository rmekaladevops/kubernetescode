[image](https://github.com/user-attachments/assets/af699273-7977-4fa5-9839-fca351637449)


🔁 GitOps Flow - Step by Step:
1. Developer Pushes Code to GitHub
The developer writes application code (e.g., app.py) and pushes it to the GitHub repo (kubernetesscode).

This triggers CI/CD automation.

2. Build Docker Image
A CI job named buildimage is triggered.

This job:

Builds a Docker container image from the application code.

Pushes the image to Docker Hub with a tag (e.g., test:10).

3. Update Kubernetes Manifest
Another CI job named updatemanifest is triggered after the image is pushed.

This job:

Updates the deployment.yaml file inside the kubernetesmanifest GitHub repository.

The manifest is modified to reference the new Docker image tag (test:10).

4. Argo CD Deploys to Kubernetes
Argo CD continuously watches the kubernetesmanifest GitHub repo.

Once it detects the updated deployment.yaml, it automatically:

Pulls the new manifest.

Deploys the updated container image (test:10) to the Kubernetes cluster.

✅ Key Tools in Use:
GitHub: Source code and manifest version control.

Docker Hub: Container image registry.

CI/CD Jobs: Automate build and manifest update.

Argo CD: GitOps tool that automates Kubernetes deployments based on Git state.

