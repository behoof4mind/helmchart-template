# Helm chart repository template

This is helm-chart template project. Can be used for any Helm chart. With IITS CI workflow inside.

# Why
- To save time by automating daily routine
- To have similar CI/CD process for all projects
- To save us from human mistakes

## How to start
1. Make new GitHub repository from this template
2. Clone it
3. Replace/Put Environment Variables and secrets
   ```yaml
    # Example values
    # Don't forget to add secrets:
    # ACR_RELEASER_TOKEN
    # SLACK_BOT_TOKEN
   
    ACR_NAME: iitsc
    ACR_USER_NAME: iits-releaser
    SLACK_CHANNEL_ID: "C02AJKXC8UT"
   ```
4. Create new branch
5. Commit and push your changes
6. Check Github Actions and [Azure container registry](https://portal.azure.com/#@iits-consulting.de/resource/subscriptions/c133dc8d-be37-4a6e-8442-c0a7e38209cb/resourcegroups/iits-tech-domain/providers/Microsoft.ContainerRegistry/registries/iitsc/repository) to be sure that your chart version is released

## How to release new stable version without short SHA in the end?
1. Test your changes to be sure that your changes can be used in Production Environment
2. Make Pull-Request with one of the labels *(depends on your case)*:
   - major
   - minor
   - patch
3. Wait for **Enforce PR labels** job finish
4. Merge it
5. Check Github Actions and [Azure container registry](https://portal.azure.com/#@iits-consulting.de/resource/subscriptions/c133dc8d-be37-4a6e-8442-c0a7e38209cb/resourcegroups/iits-tech-domain/providers/Microsoft.ContainerRegistry/registries/iitsc/repository) to be sure that your chart version is released
