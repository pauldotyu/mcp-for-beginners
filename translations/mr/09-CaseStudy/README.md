<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "873741da08dd6537858d5e14c3a386e1",
  "translation_date": "2025-07-14T05:44:07+00:00",
  "source_file": "09-CaseStudy/README.md",
  "language_code": "mr"
}
-->
# MCP क्रियेत: वास्तविक जगातील केस स्टडीज

Model Context Protocol (MCP) AI अनुप्रयोगांना डेटा, साधने आणि सेवा यांच्याशी संवाद साधण्याच्या पद्धतीत बदल घडवत आहे. या विभागात विविध उद्योगांतील MCP च्या व्यावहारिक वापराचे वास्तविक जगातील केस स्टडीज सादर केले आहेत.

## आढावा

हा विभाग MCP च्या अंमलबजावणीचे ठोस उदाहरणे दाखवतो, ज्यात संस्थांनी या प्रोटोकॉलचा वापर करून कसे क्लिष्ट व्यावसायिक आव्हाने सोडवली आहेत हे अधोरेखित केले आहे. या केस स्टडीजचा अभ्यास करून तुम्हाला MCP च्या बहुमुखीपणा, विस्तारक्षमतेचा आणि व्यावहारिक फायद्यांचा अनुभव येईल.

## मुख्य शिकण्याचे उद्दिष्टे

या केस स्टडीजचा अभ्यास करून तुम्ही:

- MCP कसा विशिष्ट व्यावसायिक समस्या सोडवण्यासाठी वापरता येतो हे समजून घ्याल
- वेगवेगळ्या एकत्रीकरण पद्धती आणि आर्किटेक्चरल दृष्टिकोनाबद्दल शिकाल
- एंटरप्राइझ वातावरणात MCP अंमलबजावणीसाठी सर्वोत्तम पद्धती ओळखाल
- वास्तविक अंमलबजावणीतील आव्हाने आणि उपाय याबाबत अंतर्दृष्टी मिळवाल
- तुमच्या स्वतःच्या प्रकल्पांमध्ये समान पद्धती वापरण्याच्या संधी ओळखाल

## वैशिष्ट्यीकृत केस स्टडीज

### 1. [Azure AI Travel Agents – Reference Implementation](./travelagentsample.md)

हा केस स्टडी Microsoft च्या सर्वसमावेशक संदर्भ सोल्यूशनचा अभ्यास करतो, ज्यात MCP, Azure OpenAI आणि Azure AI Search वापरून मल्टी-एजंट, AI-चालित प्रवास नियोजन अनुप्रयोग कसा तयार करायचा हे दाखवले आहे. प्रकल्पात खालील बाबी दाखविल्या आहेत:

- MCP द्वारे मल्टी-एजंट समन्वय
- Azure AI Search सह एंटरप्राइझ डेटा एकत्रीकरण
- Azure सेवा वापरून सुरक्षित, विस्तारक्षम आर्किटेक्चर
- पुनर्वापरयोग्य MCP घटकांसह विस्तारयोग्य साधने
- Azure OpenAI द्वारे चालवलेले संवादात्मक वापरकर्ता अनुभव

या आर्किटेक्चर आणि अंमलबजावणी तपशीलांमुळे MCP ला समन्वय स्तर म्हणून वापरून क्लिष्ट मल्टी-एजंट सिस्टम कशा तयार करायच्या याबाबत मौल्यवान माहिती मिळते.

### 2. [Updating Azure DevOps Items from YouTube Data](./UpdateADOItemsFromYT.md)

हा केस स्टडी MCP चा वापर करून वर्कफ्लो प्रक्रिया स्वयंचलित करण्याचा व्यावहारिक उपयोग दाखवतो. यात दाखवले आहे की MCP साधने कशी वापरता येतात:

- ऑनलाइन प्लॅटफॉर्म्स (YouTube) मधून डेटा काढण्यासाठी
- Azure DevOps प्रणालीतील वर्क आयटम्स अपडेट करण्यासाठी
- पुनरावृत्तीयोग्य स्वयंचलित वर्कफ्लो तयार करण्यासाठी
- वेगवेगळ्या प्रणालींमधील डेटा एकत्रित करण्यासाठी

हा उदाहरण दाखवतो की अगदी सोप्या MCP अंमलबजावणीनेही नियमित कामे स्वयंचलित करून आणि प्रणालींमधील डेटा सुसंगतता सुधारून मोठा कार्यक्षमता लाभ मिळवता येतो.

### 3. [Real-Time Documentation Retrieval with MCP](./docs-mcp/README.md)

हा केस स्टडी तुम्हाला Python कन्सोल क्लायंट वापरून Model Context Protocol (MCP) सर्व्हरशी कनेक्ट होऊन Microsoft च्या संदर्भातील रिअल-टाइम, संदर्भ-आधारित दस्तऐवज कसे मिळवायचे आणि लॉग करायचे हे शिकवतो. तुम्ही शिकाल:

- Python क्लायंट आणि अधिकृत MCP SDK वापरून MCP सर्व्हरशी कनेक्ट होणे
- कार्यक्षम, रिअल-टाइम डेटा मिळवण्यासाठी स्ट्रीमिंग HTTP क्लायंट वापरणे
- सर्व्हरवरील दस्तऐवज साधने कॉल करून प्रतिसाद थेट कन्सोलवर लॉग करणे
- टर्मिनल सोडल्याशिवाय अद्ययावत Microsoft दस्तऐवज तुमच्या वर्कफ्लोमध्ये समाकलित करणे

या प्रकरणात एक हाताळणी असाइनमेंट, एक लहान कार्यरत कोड नमुना आणि अधिक सखोल शिकण्यासाठी अतिरिक्त संसाधने दिली आहेत. संपूर्ण मार्गदर्शन आणि कोड पाहण्यासाठी लिंक केलेल्या प्रकरणाचा अभ्यास करा, ज्यामुळे MCP कन्सोल-आधारित वातावरणात दस्तऐवज प्रवेश आणि विकसक उत्पादकता कशी बदलू शकते हे समजेल.

### 4. [Interactive Study Plan Generator Web App with MCP](./docs-mcp/README.md)

हा केस स्टडी Chainlit आणि Model Context Protocol (MCP) वापरून कोणत्याही विषयासाठी वैयक्तिकृत अभ्यास योजना तयार करणारी संवादात्मक वेब अॅप कशी तयार करायची हे दाखवतो. वापरकर्ते विषय (उदा. "AI-900 certification") आणि अभ्यास कालावधी (उदा. 8 आठवडे) निर्दिष्ट करू शकतात, आणि अॅप आठवड्यांनिहाय शिफारस केलेले सामग्रीचे विहंगावलोकन देते. Chainlit संवादात्मक चॅट इंटरफेस सक्षम करतो, ज्यामुळे अनुभव आकर्षक आणि अनुकूलनीय होतो.

- Chainlit द्वारे चालवलेले संवादात्मक वेब अॅप
- विषय आणि कालावधीसाठी वापरकर्ता-चालित प्रॉम्प्ट्स
- MCP वापरून आठवड्यांनिहाय सामग्री शिफारसी
- चॅट इंटरफेसमध्ये रिअल-टाइम, अनुकूल प्रतिसाद

हा प्रकल्प दाखवतो की संवादात्मक AI आणि MCP कसे एकत्र करून आधुनिक वेब वातावरणात गतिशील, वापरकर्ता-चालित शैक्षणिक साधने तयार करता येतात.

### 5. [In-Editor Docs with MCP Server in VS Code](./docs-mcp/README.md)

हा केस स्टडी दाखवतो की तुम्ही MCP सर्व्हर वापरून Microsoft Learn Docs थेट VS Code मध्ये कसे आणू शकता—ब्राउझर टॅब्स बदलण्याची गरज नाही! तुम्हाला कसे करता येईल ते पाहाल:

- MCP पॅनेल किंवा कमांड पॅलेट वापरून VS Code मध्ये त्वरित दस्तऐवज शोधणे आणि वाचणे
- दस्तऐवज संदर्भित करणे आणि README किंवा कोर्स मार्कडाउन फाइल्समध्ये थेट दुवे समाविष्ट करणे
- GitHub Copilot आणि MCP एकत्र वापरून अखंड, AI-चालित दस्तऐवज आणि कोड वर्कफ्लो तयार करणे
- रिअल-टाइम अभिप्राय आणि Microsoft-स्त्रोत अचूकतेसह तुमचे दस्तऐवज सत्यापित आणि सुधारित करणे
- सतत दस्तऐवज सत्यापनासाठी MCP चे GitHub वर्कफ्लोशी समाकलन

अंमलबजावणीमध्ये समाविष्ट आहे:
- सोप्या सेटअपसाठी `.vscode/mcp.json` कॉन्फिगरेशनचे उदाहरण
- इन-एडिटर अनुभवाचे स्क्रीनशॉट-आधारित मार्गदर्शन
- Copilot आणि MCP एकत्र वापरण्यासाठी टिप्स ज्यामुळे जास्तीत जास्त उत्पादकता मिळते

हा प्रकरण कोर्स लेखक, दस्तऐवज लेखक आणि विकसकांसाठी आदर्श आहे जे दस्तऐवज, Copilot आणि सत्यापन साधने वापरताना त्यांच्या संपादकात लक्ष केंद्रित ठेवू इच्छितात—हे सर्व MCP द्वारे समर्थित आहे.

### 6. [APIM MCP Server Creation](./apimsample.md)

हा केस स्टडी Azure API Management (APIM) वापरून MCP सर्व्हर कसा तयार करायचा याबाबत टप्प्याटप्प्याने मार्गदर्शन करतो. यात समाविष्ट आहे:

- Azure API Management मध्ये MCP सर्व्हर सेटअप करणे
- API ऑपरेशन्सना MCP साधनांप्रमाणे एक्सपोज करणे
- दर मर्यादा आणि सुरक्षा धोरणे कॉन्फिगर करणे
- Visual Studio Code आणि GitHub Copilot वापरून MCP सर्व्हरची चाचणी करणे

हे उदाहरण दाखवते की Azure च्या क्षमतांचा वापर करून कसे एक मजबूत MCP सर्व्हर तयार करता येतो, ज्यामुळे AI प्रणालींचे एंटरप्राइझ API सोबत एकत्रीकरण सुधारते.

## निष्कर्ष

हे केस स्टडीज Model Context Protocol च्या बहुमुखीपणा आणि वास्तविक जगातील व्यावहारिक वापर दाखवतात. क्लिष्ट मल्टी-एजंट सिस्टमपासून ते लक्षित स्वयंचलित वर्कफ्लोपर्यंत, MCP AI प्रणालींना आवश्यक साधने आणि डेटा जोडण्यासाठी एक मानकीकृत मार्ग प्रदान करतो ज्यामुळे मूल्य निर्माण होते.

या अंमलबजावणींचा अभ्यास करून तुम्हाला आर्किटेक्चरल पॅटर्न्स, अंमलबजावणी धोरणे आणि सर्वोत्तम पद्धती याबाबत अंतर्दृष्टी मिळेल, ज्याचा वापर तुम्ही तुमच्या स्वतःच्या MCP प्रकल्पांमध्ये करू शकता. उदाहरणे दाखवतात की MCP फक्त सैद्धांतिक चौकट नाही तर वास्तविक व्यावसायिक आव्हानांसाठी व्यावहारिक उपाय आहे.

## अतिरिक्त संसाधने

- [Azure AI Travel Agents GitHub Repository](https://github.com/Azure-Samples/azure-ai-travel-agents)
- [Azure DevOps MCP Tool](https://github.com/microsoft/azure-devops-mcp)
- [Playwright MCP Tool](https://github.com/microsoft/playwright-mcp)
- [Microsoft Docs MCP Server](https://github.com/MicrosoftDocs/mcp)
- [MCP Community Examples](https://github.com/microsoft/mcp)

पुढे: Hands on Lab [Streamlining AI Workflows: Building an MCP Server with AI Toolkit](../10-StreamliningAIWorkflowsBuildingAnMCPServerWithAIToolkit/README.md)

**अस्वीकरण**:  
हा दस्तऐवज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून अनुवादित केला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात घ्या की स्वयंचलित अनुवादांमध्ये चुका किंवा अचूकतेची कमतरता असू शकते. मूळ दस्तऐवज त्याच्या स्थानिक भाषेत अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी अनुवाद करण्याची शिफारस केली जाते. या अनुवादाच्या वापरामुळे उद्भवलेल्या कोणत्याही गैरसमजुती किंवा चुकीच्या अर्थलागी आम्ही जबाबदार नाही.