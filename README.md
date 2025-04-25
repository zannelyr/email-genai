# Generate Email Template Notebook

This notebook automates the process of:
1. Downloading a JSON template and associated images from an Azure ML datastore.
2. Running the JSON and images through Azure Cognitive Services to analyze image features.
3. Matching the images to specific sections in the JSON.
4. Generating a final HTML email by transforming each JSON section into HTML.

## Prerequisites
- Azure Subscription
- [Azure ML Python SDK](https://learn.microsoft.com/azure/machine-learning/how-to-configure-environment#install-the-sdk)  
- [Azure Cognitive Services Computer Vision Client](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/)  
- [Azure OpenAI SDK or Azure AI Inference](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource)  
- Access to your Azure ML workspace config.

## Usage
1. Open the notebook in VS Code with a compatible Python environment.  
2. Update your credentials (endpoint, keys) for:
   - Azure ML `Workspace.from_config()`
   - Azure Computer Vision
   - Azure OpenAI client
3. Execute the cells from top to bottom:
   - Installs required packages.
   - Connects to the Azure ML workspace and downloads the JSON file + images.
   - Analyzes images, then matches them to JSON sections.
   - Generates a final HTML email and displays it.

## Files Generated
- `generated_template_with_images.json`: JSON file with mapped images.  
- `generated_email.html`: Final HTML email based on JSON sections.

## Notes
- Adjust the `file_path` and `image_dir_path` as needed.  
- Make sure to provide valid credentials for Azure resources.  
- The notebook uses GPT-based models for image matching and HTML generation—ensure your model resources are properly configured.