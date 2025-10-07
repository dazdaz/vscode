## VSCode or VSCodium
* VSCode (Visual Studio Code): A highly popular, open-source code editor developed by Microsoft. It supports a wide range of programming languages, has a rich extension ecosystem, and includes features like debugging, embedded Git control, and IntelliSense. https://code.visualstudio.com/
```bash
brew install --cask visual-studio-code
```

* VSCodium: An open-source, community-driven fork of VSCode that removes Microsoft’s proprietary elements and telemetry. It aims to provide a fully open-source alternative while maintaining most of VSCode’s functionality. VSX Registry https://open-vsx.org/ https://vscodium.com/
```bash
brew install --cask vscodium
```

## VSCode - Disable these
* Telemetry › Edit Stats : Disable
* Telemetry › Feedback : Disable


## Extensions to Install:
```text
KiloCode - obtain API key from https://app.kilocode.ai/
Mermaid Editor
Python
```

## KiloCode Configuration
```
API Provider - openrouter
OpenRouter API Key - x
Model - anthroic/claude-sonnet-4.5 or x-ai/grok-code-fast-1 or z-ai/glm-4.6
Experimental
Enable Fast Apply
Enable concurrent file edits
Enable AI image generation
- API Provider - OpenRouter
- OpenRouter API Key

Autocomplete
- Pause to Complete
- Use custom provider / Kilocode / openrouter or zai
```

## Kilo Code Provider - GCP Vertex Setup
* Google Cloud Key File Path: /Users/username/kilo-code-vertex-ai-key.json
```
export GCP_PROJECT="YOUR-PROJECT-ID"

# Enable the Vertex AI API for your project
gcloud services enable aiplatform.googleapis.com --project=$GCP_PROJECT

# Create the service account
gcloud iam service-accounts create kilo-code-vertex-ai \
  --display-name="Kilo Code Vertex AI" \
  --description="Service account for Kilo Code Vertex AI integration" \
  --project=$GCP_PROJECT

# Define the service account email using the variable
SA_EMAIL="kilo-code-vertex-ai@$GCP_PROJECT.iam.gserviceaccount.com"

# Assign the "Vertex AI User" role to the service account
gcloud projects add-iam-policy-binding $GCP_PROJECT \
  --member="serviceAccount:$SA_EMAIL" \
  --role="roles/aiplatform.user"

# Generate and download the JSON key file to your home directory
gcloud iam service-accounts keys create ~/kilo-code-vertex-ai-key.json \
  --iam-account=$SA_EMAIL \
  --project=$GCP_PROJECT
```

## VSCode Shortcuts
```
Command Palette  Ctrl+Shift+P or on MacOS (⇧⌘P) and then >
Terminal         Ctrl `

Commands : "Cloud Shell"
```

## Git
```
Download and install Git from -> https://git-scm.com/

File -> Preferences -> Settings -> Git
Path to Git executable  -> add in , into the line above
                           "git.path": "C:\\Program Files\\Git\\bin\\git.exe",
Default clone directory -> C:\gitrepo

git init
git remote add origin https://github.com/dazdaz/hellowhale.git
git pull origin master
git status
git commit -am "Added date to Dockerfile"
git push origin master
```

## Links
* https://nodejs.org/en/ Required for Cloud Shell
* https://marketplace.visualstudio.com/ Useful to browse extensions, but install inside VS Code
* https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack Node Pack for Azure
* https://code.visualstudio.com/
* https://medium.com/codingthesmartway-com-blog/getting-started-with-visual-studio-code-5f56eef810e1


Older Extensions Not Used in Years - To be re-reviewed:
```
  Ansible
  Azure Account - Azure Shell access
  Azure Dev Spaces
  Azure Terraform - Edit the system environment vairables - Add c:\apps into PATH - run "terraform init" from Azure CloudShell
  Azure CLI Tools
  Go
  Kubernetes
  Kubernetes Support
  Python
  sftp
  Terraform Azure Autocomplete
  Visual Studio Team Services
```
