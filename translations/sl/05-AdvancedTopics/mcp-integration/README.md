<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "73240f845b99df9401fffd21c09a5f7b",
  "translation_date": "2025-07-17T12:21:06+00:00",
  "source_file": "05-AdvancedTopics/mcp-integration/README.md",
  "language_code": "sl"
}
-->
# Podjetniška integracija

Pri gradnji MCP strežnikov v podjetniškem okolju je pogosto potrebno integrirati obstoječe AI platforme in storitve. Ta razdelek opisuje, kako integrirati MCP s podjetniškimi sistemi, kot sta Azure OpenAI in Microsoft AI Foundry, kar omogoča napredne AI zmogljivosti in orkestracijo orodij.

## Uvod

V tej lekciji se boste naučili, kako integrirati Model Context Protocol (MCP) s podjetniškimi AI sistemi, s poudarkom na Azure OpenAI in Microsoft AI Foundry. Te integracije vam omogočajo uporabo zmogljivih AI modelov in orodij, hkrati pa ohranjajo prilagodljivost in razširljivost MCP.

## Cilji učenja

Ob koncu te lekcije boste znali:

- Integrirati MCP z Azure OpenAI za uporabo njegovih AI zmogljivosti.
- Izvesti orkestracijo MCP orodij z Azure OpenAI.
- Združiti MCP z Microsoft AI Foundry za napredne zmogljivosti AI agentov.
- Izkoristiti Azure Machine Learning (ML) za izvajanje ML cevovodov in registracijo modelov kot MCP orodij.

## Integracija Azure OpenAI

Azure OpenAI omogoča dostop do zmogljivih AI modelov, kot je GPT-4 in drugi. Integracija MCP z Azure OpenAI vam omogoča uporabo teh modelov, hkrati pa ohranja prilagodljivost orkestracije orodij MCP.

### Implementacija v C#

V tem odseku kode prikazujemo, kako integrirati MCP z Azure OpenAI z uporabo Azure OpenAI SDK.

```csharp
// .NET Azure OpenAI Integration
using Microsoft.Mcp.Client;
using Azure.AI.OpenAI;
using Microsoft.Extensions.Configuration;
using System.Threading.Tasks;

namespace EnterpriseIntegration
{
    public class AzureOpenAiMcpClient
    {
        private readonly string _endpoint;
        private readonly string _apiKey;
        private readonly string _deploymentName;
        
        public AzureOpenAiMcpClient(IConfiguration config)
        {
            _endpoint = config["AzureOpenAI:Endpoint"];
            _apiKey = config["AzureOpenAI:ApiKey"];
            _deploymentName = config["AzureOpenAI:DeploymentName"];
        }
        
        public async Task<string> GetCompletionWithToolsAsync(string prompt, params string[] allowedTools)
        {
            // Create OpenAI client
            var client = new OpenAIClient(new Uri(_endpoint), new AzureKeyCredential(_apiKey));
            
            // Create completion options with tools
            var completionOptions = new ChatCompletionsOptions
            {
                DeploymentName = _deploymentName,
                Messages = { new ChatMessage(ChatRole.User, prompt) },
                Temperature = 0.7f,
                MaxTokens = 800
            };
            
            // Add tool definitions
            foreach (var tool in allowedTools)
            {
                completionOptions.Tools.Add(new ChatCompletionsFunctionToolDefinition
                {
                    Name = tool,
                    // In a real implementation, you'd add the tool schema here
                });
            }
            
            // Get completion response
            var response = await client.GetChatCompletionsAsync(completionOptions);
            
            // Handle tool calls in the response
            foreach (var toolCall in response.Value.Choices[0].Message.ToolCalls)
            {
                // Implementation to handle Azure OpenAI tool calls with MCP
                // ...
            }
            
            return response.Value.Choices[0].Message.Content;
        }
    }
}
```

V zgornji kodi smo:

- Konfigurirali Azure OpenAI odjemalca z endpointom, imenom namestitve in API ključem.
- Ustvarili metodo `GetCompletionWithToolsAsync` za pridobivanje zaključkov z podporo orodij.
- Obdelali klice orodij v odgovoru.

Priporočamo, da implementirate dejansko logiko obdelave orodij glede na vašo specifično nastavitev MCP strežnika.

## Integracija Microsoft AI Foundry

Azure AI Foundry ponuja platformo za gradnjo in uvajanje AI agentov. Integracija MCP z AI Foundry vam omogoča uporabo njegovih zmogljivosti, hkrati pa ohranja prilagodljivost MCP.

V spodnji kodi razvijamo integracijo agenta, ki obdeluje zahteve in upravlja klice orodij z uporabo MCP.

### Implementacija v Javi

```java
// Java AI Foundry Agent Integration
package com.example.mcp.enterprise;

import com.microsoft.aifoundry.AgentClient;
import com.microsoft.aifoundry.AgentToolResponse;
import com.microsoft.aifoundry.models.AgentRequest;
import com.microsoft.aifoundry.models.AgentResponse;
import com.mcp.client.McpClient;
import com.mcp.tools.ToolRequest;
import com.mcp.tools.ToolResponse;

public class AIFoundryMcpBridge {
    private final AgentClient agentClient;
    private final McpClient mcpClient;
    
    public AIFoundryMcpBridge(String aiFoundryEndpoint, String mcpServerUrl) {
        this.agentClient = new AgentClient(aiFoundryEndpoint);
        this.mcpClient = new McpClient.Builder()
            .setServerUrl(mcpServerUrl)
            .build();
    }
    
    public AgentResponse processAgentRequest(AgentRequest request) {
        // Process the AI Foundry Agent request
        AgentResponse initialResponse = agentClient.processRequest(request);
        
        // Check if the agent requested to use tools
        if (initialResponse.getToolCalls() != null && !initialResponse.getToolCalls().isEmpty()) {
            // For each tool call, route it to the appropriate MCP tool
            for (AgentToolCall toolCall : initialResponse.getToolCalls()) {
                String toolName = toolCall.getName();
                Map<String, Object> parameters = toolCall.getArguments();
                
                // Execute the tool using MCP
                ToolResponse mcpResponse = mcpClient.executeTool(toolName, parameters);
                
                // Create tool response for AI Foundry
                AgentToolResponse toolResponse = new AgentToolResponse(
                    toolCall.getId(),
                    mcpResponse.getResult()
                );
                
                // Submit tool response back to the agent
                initialResponse = agentClient.submitToolResponse(
                    request.getConversationId(), 
                    toolResponse
                );
            }
        }
        
        return initialResponse;
    }
}
```

V zgornji kodi smo:

- Ustvarili razred `AIFoundryMcpBridge`, ki integrira tako AI Foundry kot MCP.
- Implementirali metodo `processAgentRequest`, ki obdeluje zahtevo AI Foundry agenta.
- Obdelali klice orodij z izvajanjem prek MCP odjemalca in posredovanjem rezultatov nazaj AI Foundry agentu.

## Integracija MCP z Azure ML

Integracija MCP z Azure Machine Learning (ML) vam omogoča uporabo zmogljivih ML zmogljivosti Azure, hkrati pa ohranja prilagodljivost MCP. Ta integracija se lahko uporablja za izvajanje ML cevovodov, registracijo modelov kot orodij in upravljanje računalniških virov.

### Implementacija v Pythonu

```python
# Python Azure AI Integration
from mcp_client import McpClient
from azure.ai.ml import MLClient
from azure.identity import DefaultAzureCredential
from azure.ai.ml.entities import Environment, AmlCompute
import os
import asyncio

class EnterpriseAiIntegration:
    def __init__(self, mcp_server_url, subscription_id, resource_group, workspace_name):
        # Set up MCP client
        self.mcp_client = McpClient(server_url=mcp_server_url)
        
        # Set up Azure ML client
        self.credential = DefaultAzureCredential()
        self.ml_client = MLClient(
            self.credential,
            subscription_id,
            resource_group,
            workspace_name
        )
    
    async def execute_ml_pipeline(self, pipeline_name, input_data):
        """Executes an ML pipeline in Azure ML"""
        # First process the input data using MCP tools
        processed_data = await self.mcp_client.execute_tool(
            "dataPreprocessor",
            {
                "data": input_data,
                "operations": ["normalize", "clean", "transform"]
            }
        )
        
        # Submit the pipeline to Azure ML
        pipeline_job = self.ml_client.jobs.create_or_update(
            entity={
                "name": pipeline_name,
                "display_name": f"MCP-triggered {pipeline_name}",
                "experiment_name": "mcp-integration",
                "inputs": {
                    "processed_data": processed_data.result
                }
            }
        )
        
        # Return job information
        return {
            "job_id": pipeline_job.id,
            "status": pipeline_job.status,
            "creation_time": pipeline_job.creation_context.created_at
        }
    
    async def register_ml_model_as_tool(self, model_name, model_version="latest"):
        """Registers an Azure ML model as an MCP tool"""
        # Get model details
        if model_version == "latest":
            model = self.ml_client.models.get(name=model_name, label="latest")
        else:
            model = self.ml_client.models.get(name=model_name, version=model_version)
        
        # Create deployment environment
        env = Environment(
            name="mcp-model-env",
            conda_file="./environments/inference-env.yml"
        )
        
        # Set up compute
        compute = self.ml_client.compute.get("mcp-inference")
        
        # Deploy model as online endpoint
        deployment = self.ml_client.online_deployments.create_or_update(
            endpoint_name=f"mcp-{model_name}",
            deployment={
                "name": f"mcp-{model_name}-deployment",
                "model": model.id,
                "environment": env,
                "compute": compute,
                "scale_settings": {
                    "scale_type": "auto",
                    "min_instances": 1,
                    "max_instances": 3
                }
            }
        )
        
        # Create MCP tool schema based on model schema
        tool_schema = {
            "type": "object",
            "properties": {},
            "required": []
        }
        
        # Add input properties based on model schema
        for input_name, input_spec in model.signature.inputs.items():
            tool_schema["properties"][input_name] = {
                "type": self._map_ml_type_to_json_type(input_spec.type)
            }
            tool_schema["required"].append(input_name)
        
        # Register as MCP tool
        # In a real implementation, you would create a tool that calls the endpoint
        return {
            "model_name": model_name,
            "model_version": model.version,
            "endpoint": deployment.endpoint_uri,
            "tool_schema": tool_schema
        }
    
    def _map_ml_type_to_json_type(self, ml_type):
        """Maps ML data types to JSON schema types"""
        mapping = {
            "float": "number",
            "int": "integer",
            "bool": "boolean",
            "str": "string",
            "object": "object",
            "array": "array"
        }
        return mapping.get(ml_type, "string")
```

V zgornji kodi smo:

- Ustvarili razred `EnterpriseAiIntegration`, ki integrira MCP z Azure ML.
- Implementirali metodo `execute_ml_pipeline`, ki obdeluje vhodne podatke z MCP orodji in pošilja ML cevovod v Azure ML.
- Implementirali metodo `register_ml_model_as_tool`, ki registrira Azure ML model kot MCP orodje, vključno z ustvarjanjem potrebnega okolja za namestitev in računalniških virov.
- Preslikali Azure ML tipe podatkov v JSON sheme za registracijo orodij.
- Uporabili asinhrono programiranje za obravnavo potencialno dolgotrajnih operacij, kot so izvajanje ML cevovodov in registracija modelov.

## Kaj sledi

- [5.2 Večmodalnost](../mcp-multi-modality/README.md)

**Omejitev odgovornosti**:  
Ta dokument je bil preveden z uporabo storitve za avtomatski prevod AI [Co-op Translator](https://github.com/Azure/co-op-translator). Čeprav si prizadevamo za natančnost, vas opozarjamo, da lahko avtomatizirani prevodi vsebujejo napake ali netočnosti. Izvirni dokument v njegovem izvirnem jeziku velja za avtoritativni vir. Za pomembne informacije priporočamo strokovni človeški prevod. Za morebitna nesporazume ali napačne interpretacije, ki izhajajo iz uporabe tega prevoda, ne odgovarjamo.