<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9b03446058b4eed46928ae5e46325ea0",
  "translation_date": "2025-10-11T11:24:59+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "et"
}
-->
# Kursuse Seadistamine

## Sissejuhatus

Selles õppetükis käsitletakse, kuidas käivitada selle kursuse koodinäiteid.

## Liitu teiste õppijatega ja saa abi

Enne kui hakkad oma repositooriumi kloonima, liitu [AI Agents For Beginners Discord kanaliga](https://aka.ms/ai-agents/discord), et saada abi seadistamisel, esitada küsimusi kursuse kohta või luua ühendust teiste õppijatega.

## Klooni või hargi see repositoorium

Alustamiseks klooni või hargi GitHubi repositoorium. See loob sinu enda versiooni kursuse materjalist, et saaksid koodi käivitada, testida ja kohandada!

Seda saab teha, klõpsates lingil <a href="https://github.com/microsoft/ai-agents-for-beginners/fork" target="_blank">hargi repositoorium</a>.

Nüüd peaks sul olema selle kursuse enda hargitud versioon järgmisel lingil:

![Hargitud Repositoorium](../../../translated_images/forked-repo.33f27ca1901baa6a5e13ec3eb1f0ddd3a44d936d91cc8cfb19bfdb9688bd2c3d.et.png)

## Koodi käivitamine

See kursus pakub Jupyter Notebookide seeriat, mida saad käivitada, et saada praktilisi kogemusi AI agentide loomisel.

Koodinäited kasutavad järgmist:

**Nõuab GitHubi kontot - Tasuta**:

1) Semantic Kernel Agent Framework + GitHub Models Marketplace. Märgistatud kui (semantic-kernel.ipynb)
2) AutoGen Framework + GitHub Models Marketplace. Märgistatud kui (autogen.ipynb)

**Nõuab Azure'i tellimust**:
3) Azure AI Foundry + Azure AI Agent Service. Märgistatud kui (azureaiagent.ipynb)

Soovitame proovida kõiki kolme näidet, et näha, milline neist sobib sulle kõige paremini.

Valik, mille teed, määrab, milliseid seadistamise samme allpool järgida:

## Nõuded

- Python 3.12+
  - **NOTE**: Kui sul pole Python 3.12 paigaldatud, veendu, et paigaldad selle. Seejärel loo oma venv, kasutades python3.12, et tagada õige versioonide paigaldamine requirements.txt failist.
  
    >Näide

    Loo Python venv kataloog:

    ``` bash
    python3 -m venv venv
    ```

    Seejärel aktiveeri venv keskkond:

    macOS ja Linux

    ```bash
    source venv/bin/activate
    ```
  
    Windows

    ```bash
    venv\Scripts\activate
    ```

- GitHubi konto - Juurdepääsuks GitHub Models Marketplace'ile
- Azure'i tellimus - Juurdepääsuks Azure AI Foundry'le
- Azure AI Foundry konto - Juurdepääsuks Azure AI Agent Service'ile

Me oleme lisanud `requirements.txt` faili selle repositooriumi juurkausta, mis sisaldab kõiki vajalikke Python pakette koodinäidete käivitamiseks.

Sa saad need paigaldada, käivitades järgmise käsu oma terminalis repositooriumi juurkaustas:

```bash
pip install -r requirements.txt
```
Soovitame luua Python virtuaalse keskkonna, et vältida konflikte ja probleeme.

## VSCode seadistamine
Veendu, et kasutad õiget Python versiooni VSCode'is.

![image](https://github.com/user-attachments/assets/a85e776c-2edb-4331-ae5b-6bfdfb98ee0e)

## Seadistamine GitHub Models näidete jaoks 

### Samm 1: Hangi oma GitHubi isiklik juurdepääsutoken (PAT)

See kursus kasutab GitHub Models Marketplace'i, mis pakub tasuta juurdepääsu suurtele keelemudelitele (LLM), mida kasutad AI agentide loomiseks.

GitHub Models kasutamiseks pead looma [GitHubi isikliku juurdepääsutokeni](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

Seda saab teha, minnes oma <a href="https://github.com/settings/personal-access-tokens" target="_blank">isikliku juurdepääsutokeni seadistuste</a> lehele oma GitHubi kontol.

Palun järgi [väikseima privileegi põhimõtet](https://docs.github.com/en/get-started/learning-to-code/storing-your-secrets-safely) tokeni loomisel. See tähendab, et peaksid andma tokenile ainult need õigused, mis on vajalikud selle kursuse koodinäidete käivitamiseks.

1. Vali ekraani vasakul küljel **Developer settings** alt `Fine-grained tokens` valik.
   ![](../../../translated_images/profile_developer_settings.410a859fe749c755c859d414294c5908e307222b2c61819c3203bbeed4470e25.et.png)

    Seejärel vali `Generate new token`.

    ![Loo Token](../../../translated_images/fga_new_token.1c1a234afe202ab37483944a291ee80c1868e1e78082fd6bd4180fea5d5a15b4.et.png)

2. Sisesta tokenile kirjeldav nimi, mis kajastab selle eesmärki, et seda oleks hiljem lihtne tuvastada.


    🔐 Tokeni kestuse soovitus

    Soovitatav kestus: 30 päeva
    Turvalisuse suurendamiseks võid valida lühema perioodi—näiteks 7 päeva 🛡️
    See on suurepärane viis seada isiklik eesmärk ja lõpetada kursus, hoides õppimise hoogu 🚀.

    ![Tokeni nimi ja aegumiskuupäev](../../../translated_images/token-name-expiry-date.a095fb0de63868640a4c82d6b1bbc92b482930a663917a5983a3c7cd1ef86b77.et.png)

3. Piira tokeni ulatust selle repositooriumi hargile.

    ![Piira ulatust hargitud repositooriumile](../../../translated_images/token_repository_limit.924ade5e11d9d8bb6cd21293987e4579dea860e2ba66d607fb46e49524d53644.et.png)

4. Piira tokeni õigusi: **Permissions** all klõpsa **Account** vahekaardil ja vajuta "+ Add permissions" nuppu. Ilmub rippmenüü. Otsi **Models** ja märgi selle kast.
    ![Lisa Models õigused](../../../translated_images/add_models_permissions.c0c44ed8b40fc143dc87792da9097d715b7de938354e8f771d65416ecc7816b8.et.png)

5. Kontrolli enne tokeni loomist vajalikke õigusi. ![Kontrolli õigusi](../../../translated_images/verify_permissions.06bd9e43987a8b219f171bbcf519e45ababae35b844f5e9757e10afcb619b936.et.png)

6. Enne tokeni loomist veendu, et oled valmis tokeni turvaliselt salvestama, näiteks paroolihalduri seifi, kuna seda ei kuvata uuesti pärast loomist. ![Salvesta token turvaliselt](../../../translated_images/store_token_securely.08ee2274c6ad6caf3482f1cd1bad7ca3fdca1ce737bc485bfa6499c84297c789.et.png)

Kopeeri oma äsja loodud token. Nüüd lisad selle kursuse `.env` faili.


### Samm 2: Loo oma `.env` fail

`.env` faili loomiseks käivita järgmine käsk oma terminalis.

```bash
cp .env.example .env
```

See kopeerib näidisfaili ja loob `.env` faili sinu kataloogi, kuhu saad täita keskkonnamuutujate väärtused.

Kopeeritud tokeniga ava `.env` fail oma lemmiktekstiredaktoris ja kleebi token `GITHUB_TOKEN` väljale.
![GitHub Token väli](../../../translated_images/github_token_field.20491ed3224b5f4ab24d10ced7a68c4aba2948fe8999cfc8675edaa16f5e5681.et.png)


Nüüd peaksid saama käivitada selle kursuse koodinäiteid.

## Seadistamine Azure AI Foundry ja Azure AI Agent Service näidete jaoks

### Samm 1: Hangi oma Azure'i projekti lõpp-punkt


Järgi juhiseid Azure AI Foundry keskuse ja projekti loomiseks siin: [Hub resources overview](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/ai-resources)


Kui oled oma projekti loonud, pead hankima projekti ühenduse stringi.

Seda saab teha, minnes **Overview** lehele oma projektis Azure AI Foundry portaalis.

![Projekti ühenduse string](../../../translated_images/project-endpoint.8cf04c9975bbfbf18f6447a599550edb052e52264fb7124d04a12e6175e330a5.et.png)

### Samm 2: Loo oma `.env` fail

`.env` faili loomiseks käivita järgmine käsk oma terminalis.

```bash
cp .env.example .env
```

See kopeerib näidisfaili ja loob `.env` faili sinu kataloogi, kuhu saad täita keskkonnamuutujate väärtused.

Kopeeritud tokeniga ava `.env` fail oma lemmiktekstiredaktoris ja kleebi token `PROJECT_ENDPOINT` väljale.

### Samm 3: Logi sisse Azure'i

Turvalisuse parima tava järgi kasutame [võtmeta autentimist](https://learn.microsoft.com/azure/developer/ai/keyless-connections?tabs=csharp%2Cazure-cli?WT.mc_id=academic-105485-koreyst), et autentida Azure OpenAI Microsoft Entra ID-ga. 

Järgmise sammuna ava terminal ja käivita `az login --use-device-code`, et logida sisse oma Azure'i kontole.

Kui oled sisse loginud, vali oma tellimus terminalis.


## Täiendavad keskkonnamuutujad - Azure Search ja Azure OpenAI 

Agentic RAG õppetüki - Õppetund 5 - jaoks on näited, mis kasutavad Azure Searchi ja Azure OpenAI-d.

Kui soovid neid näiteid käivitada, pead lisama järgmised keskkonnamuutujad oma `.env` faili:

### Ülevaate leht (Projekt)

- `AZURE_SUBSCRIPTION_ID` - Vaata **Project details** **Overview** lehel oma projektis.

- `AZURE_AI_PROJECT_NAME` - Vaata oma projekti **Overview** lehe ülaosas.

- `AZURE_OPENAI_SERVICE` - Leia see **Included capabilities** vahekaardilt **Azure OpenAI Service** **Overview** lehel.

### Halduse keskus

- `AZURE_OPENAI_RESOURCE_GROUP` - Mine **Project properties** **Overview** lehel **Management Center**-is.

- `GLOBAL_LLM_SERVICE` - **Connected resources** all leia **Azure AI Services** ühenduse nimi. Kui pole loetletud, kontrolli **Azure portaalis** oma ressursigrupis AI Services ressursi nime.

### Mudelid + Lõpp-punktid leht

- `AZURE_OPENAI_EMBEDDING_DEPLOYMENT_NAME` - Vali oma embedding mudel (nt `text-embedding-ada-002`) ja pane tähele **Deployment name** mudeli detailidest.

- `AZURE_OPENAI_CHAT_DEPLOYMENT_NAME` - Vali oma chat mudel (nt `gpt-4o-mini`) ja pane tähele **Deployment name** mudeli detailidest.

### Azure portaal

- `AZURE_OPENAI_ENDPOINT` - Otsi **Azure AI services**, klõpsa sellel, mine **Resource Management**, **Keys and Endpoint**, kerige alla "Azure OpenAI endpoints" ja kopeeri see, mis ütleb "Language APIs".

- `AZURE_OPENAI_API_KEY` - Samalt ekraanilt kopeeri KEY 1 või KEY 2.

- `AZURE_SEARCH_SERVICE_ENDPOINT` - Leia oma **Azure AI Search** ressurss, klõpsa sellel ja vaata **Overview**.

- `AZURE_SEARCH_API_KEY` - Seejärel mine **Settings** ja siis **Keys**, et kopeerida primaarne või sekundaarne admini võti.

### Väline veebileht

- `AZURE_OPENAI_API_VERSION` - Külastage [API versiooni elutsükli](https://learn.microsoft.com/en-us/azure/ai-services/openai/api-version-deprecation#latest-ga-api-release) lehte **Latest GA API release** all.

### Võtmeta autentimise seadistamine

Selle asemel, et oma mandaate kõvakodeerida, kasutame võtmeta ühendust Azure OpenAI-ga. Selleks impordime `DefaultAzureCredential` ja hiljem kutsume `DefaultAzureCredential` funktsiooni, et saada mandaadi.

```python
from azure.identity import DefaultAzureCredential, InteractiveBrowserCredential
```

## Jäid kuskile toppama?

Kui sul on probleeme selle seadistuse käivitamisega, liitu meiega <a href="https://discord.gg/kzRShWzttr" target="_blank">Azure AI Community Discordis</a> või <a href="https://github.com/microsoft/ai-agents-for-beginners/issues?WT.mc_id=academic-105485-koreyst" target="_blank">loo probleem</a>.

## Järgmine õppetund

Nüüd oled valmis käivitama selle kursuse koodi. Head õppimist AI agentide maailma avastamisel! 

[AI agentide sissejuhatus ja agentide kasutusjuhtumid](../01-intro-to-ai-agents/README.md)

---

**Lahtiütlus**:  
See dokument on tõlgitud AI tõlketeenuse [Co-op Translator](https://github.com/Azure/co-op-translator) abil. Kuigi püüame tagada täpsust, palume arvestada, et automaatsed tõlked võivad sisaldada vigu või ebatäpsusi. Algne dokument selle algses keeles tuleks pidada autoriteetseks allikaks. Olulise teabe puhul soovitame kasutada professionaalset inimtõlget. Me ei vastuta selle tõlke kasutamisest tulenevate arusaamatuste või valesti tõlgenduste eest.