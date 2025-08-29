<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "14b2a7f1c63202920bd98eeb913f5614",
  "translation_date": "2025-08-28T02:23:40+00:00",
  "source_file": "5-Data-Science-In-Cloud/18-Low-Code/README.md",
  "language_code": "tl"
}
-->
# Data Science sa Cloud: Ang "Low code/No code" na Paraan

|![ Sketchnote ni [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/18-DataScience-Cloud.png)|
|:---:|
| Data Science sa Cloud: Low Code - _Sketchnote ni [@nitya](https://twitter.com/nitya)_ |

Talaan ng Nilalaman:

- [Data Science sa Cloud: Ang "Low code/No code" na Paraan](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [Pre-Lecture Quiz](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [1. Panimula](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [1.1 Ano ang Azure Machine Learning?](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [1.2 Ang Proyekto sa Prediksyon ng Heart Failure:](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [1.3 Ang Heart Failure Dataset:](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [2. Low code/No code na Pagsasanay ng Modelo sa Azure ML Studio](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [2.1 Gumawa ng Azure ML Workspace](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [2.2 Compute Resources](../../../../5-Data-Science-In-Cloud/18-Low-Code)
      - [2.2.1 Pagpili ng tamang opsyon para sa iyong compute resources](../../../../5-Data-Science-In-Cloud/18-Low-Code)
      - [2.2.2 Paglikha ng compute cluster](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [2.3 Paglo-load ng Dataset](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [2.4 Low code/No Code na Pagsasanay gamit ang AutoML](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [3. Low code/No Code na Pag-deploy ng Modelo at Paggamit ng Endpoint](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [3.1 Pag-deploy ng Modelo](../../../../5-Data-Science-In-Cloud/18-Low-Code)
    - [3.2 Paggamit ng Endpoint](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [🚀 Hamon](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [Post-Lecture Quiz](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [Review at Pag-aaral sa Sarili](../../../../5-Data-Science-In-Cloud/18-Low-Code)
  - [Takdang Aralin](../../../../5-Data-Science-In-Cloud/18-Low-Code)

## [Pre-Lecture Quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/34)

## 1. Panimula

### 1.1 Ano ang Azure Machine Learning?

Ang Azure cloud platform ay binubuo ng mahigit 200 produkto at cloud services na dinisenyo upang makatulong sa paglikha ng mga bagong solusyon. Ang mga data scientist ay gumugugol ng maraming oras sa pag-eeksperimento at pag-preprocess ng data, pati na rin sa pagsubok ng iba't ibang uri ng model-training algorithms upang makabuo ng tumpak na mga modelo. Ang mga gawaing ito ay nakakaubos ng oras at madalas na hindi epektibo sa paggamit ng mahal na compute hardware.

Ang [Azure ML](https://docs.microsoft.com/azure/machine-learning/overview-what-is-azure-machine-learning?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109) ay isang cloud-based platform para sa pagbuo at pagpapatakbo ng mga solusyon sa machine learning sa Azure. Naglalaman ito ng malawak na hanay ng mga tampok at kakayahan na tumutulong sa mga data scientist sa paghahanda ng data, pagsasanay ng mga modelo, pag-publish ng mga predictive services, at pagsubaybay sa kanilang paggamit. Ang pinakamahalaga, pinapadali nito ang kanilang trabaho sa pamamagitan ng pag-automate ng maraming nakakaubos ng oras na gawain na kaugnay ng pagsasanay ng mga modelo; at pinapayagan silang gumamit ng cloud-based compute resources na epektibong nag-e-scale upang hawakan ang malalaking volume ng data habang nagbabayad lamang kapag ginagamit.

Ang Azure ML ay nagbibigay ng lahat ng mga tool na kailangan ng mga developer at data scientist para sa kanilang machine learning workflows. Kabilang dito ang:

- **Azure Machine Learning Studio**: Isang web portal sa Azure Machine Learning para sa low-code at no-code na mga opsyon para sa pagsasanay ng modelo, pag-deploy, automation, tracking, at asset management. Ang studio ay integrated sa Azure Machine Learning SDK para sa seamless na karanasan.
- **Jupyter Notebooks**: Mabilis na pag-prototype at pagsubok ng mga ML model.
- **Azure Machine Learning Designer**: Pinapayagan ang drag-and-drop ng mga module upang bumuo ng mga eksperimento at mag-deploy ng mga pipeline sa isang low-code na kapaligiran.
- **Automated machine learning UI (AutoML)**: Ina-automate ang mga iterative na gawain ng pagbuo ng machine learning model, na nagbibigay-daan sa paggawa ng mga ML model na may mataas na scale, kahusayan, at produktibidad, habang pinapanatili ang kalidad ng modelo.
- **Data Labelling**: Isang assisted ML tool para awtomatikong mag-label ng data.
- **Machine learning extension para sa Visual Studio Code**: Nagbibigay ng full-featured na development environment para sa pagbuo at pamamahala ng mga ML project.
- **Machine learning CLI**: Nagbibigay ng mga command para sa pamamahala ng Azure ML resources mula sa command line.
- **Integration sa open-source frameworks** tulad ng PyTorch, TensorFlow, Scikit-learn, at marami pang iba para sa pagsasanay, pag-deploy, at pamamahala ng end-to-end na proseso ng machine learning.
- **MLflow**: Isang open-source library para sa pamamahala ng life cycle ng iyong machine learning experiments. Ang **MLFlow Tracking** ay isang bahagi ng MLflow na naglo-log at sumusubaybay sa iyong training run metrics at model artifacts, anuman ang kapaligiran ng iyong eksperimento.

### 1.2 Ang Proyekto sa Prediksyon ng Heart Failure:

Walang duda na ang paggawa at pagbuo ng mga proyekto ang pinakamahusay na paraan upang subukan ang iyong mga kasanayan at kaalaman. Sa araling ito, tatalakayin natin ang dalawang magkaibang paraan ng paggawa ng isang data science project para sa prediksyon ng heart failure attacks sa Azure ML Studio, gamit ang Low code/No code at ang Azure ML SDK, tulad ng ipinapakita sa sumusunod na schema:

![project-schema](../../../../translated_images/project-schema.736f6e403f321eb48d10242b3f4334dc6ccf0eabef8ff87daf52b89781389fcb.tl.png)

Ang bawat paraan ay may kani-kaniyang kalamangan at kahinaan. Ang Low code/No code na paraan ay mas madaling simulan dahil ito ay gumagamit ng GUI (Graphical User Interface), na hindi nangangailangan ng kaalaman sa code. Ang pamamaraang ito ay nagbibigay-daan sa mabilis na pagsubok ng viability ng proyekto at sa paggawa ng POC (Proof Of Concept). Gayunpaman, habang lumalaki ang proyekto at kailangang maging handa para sa production, hindi praktikal na lumikha ng mga resources sa pamamagitan ng GUI. Kailangan nating i-automate ang lahat ng bagay nang programmatically, mula sa paglikha ng mga resources hanggang sa pag-deploy ng modelo. Dito nagiging mahalaga ang kaalaman sa paggamit ng Azure ML SDK.

|                   | Low code/No code | Azure ML SDK              |
|-------------------|------------------|---------------------------|
| Kaalaman sa code  | Hindi kailangan  | Kailangan                 |
| Oras ng pagbuo    | Mabilis at madali| Depende sa kaalaman sa code |
| Handa sa production | Hindi           | Oo                        |

### 1.3 Ang Heart Failure Dataset:

Ang cardiovascular diseases (CVDs) ang pangunahing sanhi ng kamatayan sa buong mundo, na nagdudulot ng 31% ng lahat ng pagkamatay. Ang mga environmental at behavioral risk factors tulad ng paggamit ng tabako, hindi malusog na diyeta at labis na katabaan, kawalan ng pisikal na aktibidad, at mapanganib na paggamit ng alak ay maaaring gamitin bilang mga feature para sa estimation models. Ang kakayahang matantiya ang posibilidad ng pag-develop ng CVD ay maaaring maging malaking tulong upang maiwasan ang mga atake sa mga taong may mataas na panganib.

Ang Kaggle ay nagbigay ng isang [Heart Failure dataset](https://www.kaggle.com/andrewmvd/heart-failure-clinical-data) na magagamit natin para sa proyektong ito. Maaari mo nang i-download ang dataset. Ito ay isang tabular dataset na may 13 column (12 features at 1 target variable) at 299 rows.

|    | Pangalan ng Variable       | Uri             | Deskripsyon                                               | Halimbawa         |
|----|---------------------------|-----------------|-----------------------------------------------------------|-------------------|
| 1  | age                       | numerical       | Edad ng pasyente                                         | 25                |
| 2  | anaemia                   | boolean         | Pagbaba ng red blood cells o hemoglobin                  | 0 o 1             |
| 3  | creatinine_phosphokinase  | numerical       | Antas ng CPK enzyme sa dugo                              | 542               |
| 4  | diabetes                  | boolean         | Kung may diabetes ang pasyente                           | 0 o 1             |
| 5  | ejection_fraction         | numerical       | Porsyento ng dugo na lumalabas sa puso sa bawat contraction | 45                |
| 6  | high_blood_pressure       | boolean         | Kung may hypertension ang pasyente                       | 0 o 1             |
| 7  | platelets                 | numerical       | Platelets sa dugo                                        | 149000            |
| 8  | serum_creatinine          | numerical       | Antas ng serum creatinine sa dugo                        | 0.5               |
| 9  | serum_sodium              | numerical       | Antas ng serum sodium sa dugo                            | jun               |
| 10 | sex                       | boolean         | Babae o lalaki                                           | 0 o 1             |
| 11 | smoking                   | boolean         | Kung naninigarilyo ang pasyente                          | 0 o 1             |
| 12 | time                      | numerical       | Panahon ng follow-up (araw)                              | 4                 |
|----|---------------------------|-----------------|-----------------------------------------------------------|-------------------|
| 21 | DEATH_EVENT [Target]      | boolean         | Kung namatay ang pasyente sa panahon ng follow-up         | 0 o 1             |

Kapag nakuha mo na ang dataset, maaari na nating simulan ang proyekto sa Azure.

## 2. Low code/No code na Pagsasanay ng Modelo sa Azure ML Studio

### 2.1 Gumawa ng Azure ML Workspace

Upang magsanay ng modelo sa Azure ML, kailangan mo munang gumawa ng Azure ML workspace. Ang workspace ang pangunahing resource para sa Azure Machine Learning, na nagbibigay ng sentralisadong lugar upang pamahalaan ang lahat ng artifacts na iyong nilikha kapag ginamit mo ang Azure Machine Learning. Ang workspace ay nagtatala ng kasaysayan ng lahat ng training runs, kabilang ang mga log, metrics, output, at snapshot ng iyong mga script. Ginagamit mo ang impormasyong ito upang matukoy kung aling training run ang nagbunga ng pinakamahusay na modelo. [Matuto pa](https://docs.microsoft.com/azure/machine-learning/concept-workspace?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109)

Inirerekomenda na gumamit ng pinakabagong bersyon ng browser na compatible sa iyong operating system. Ang mga sumusunod na browser ay suportado:

- Microsoft Edge (Ang bagong Microsoft Edge, pinakabagong bersyon. Hindi ang Microsoft Edge legacy)
- Safari (pinakabagong bersyon, Mac lamang)
- Chrome (pinakabagong bersyon)
- Firefox (pinakabagong bersyon)

Upang magamit ang Azure Machine Learning, gumawa ng workspace sa iyong Azure subscription. Maaari mo nang gamitin ang workspace na ito upang pamahalaan ang data, compute resources, code, modelo, at iba pang artifacts na may kaugnayan sa iyong machine learning workloads.

> **_NOTE:_** Ang iyong Azure subscription ay sisingilin ng maliit na halaga para sa data storage hangga't ang Azure Machine Learning workspace ay umiiral sa iyong subscription, kaya inirerekomenda naming tanggalin ang Azure Machine Learning workspace kapag hindi mo na ito ginagamit.

1. Mag-sign in sa [Azure portal](https://ms.portal.azure.com/) gamit ang Microsoft credentials na nauugnay sa iyong Azure subscription.
2. Piliin ang **＋Create a resource**
   
   ![workspace-1](../../../../translated_images/workspace-1.ac8694d60b073ed1ae8333d71244dc8a9b3e439d54593724f98f1beefdd27b08.tl.png)

   Maghanap ng Machine Learning at piliin ang Machine Learning tile.

   ![workspace-2](../../../../translated_images/workspace-2.ae7c486db8796147075e4a56566aa819827dd6c4c8d18d64590317c3be625f17.tl.png)

   I-click ang create button.

   ![workspace-3](../../../../translated_images/workspace-3.398ca4a5858132cce584db9df10c5a011cd9075eb182e647a77d5cac01771eea.tl.png)

   Punan ang mga setting tulad ng sumusunod:
   - Subscription: Ang iyong Azure subscription
   - Resource group: Gumawa o pumili ng resource group
   - Workspace name: Maglagay ng natatanging pangalan para sa iyong workspace
   - Region: Piliin ang pinakamalapit na rehiyon sa iyo
   - Storage account: Tandaan ang default na bagong storage account na gagawin para sa iyong workspace
   - Key vault: Tandaan ang default na bagong key vault na gagawin para sa iyong workspace
   - Application insights: Tandaan ang default na bagong application insights resource na gagawin para sa iyong workspace
   - Container registry: Wala (isa ang awtomatikong gagawin sa unang pagkakataon na mag-deploy ka ng modelo sa isang container)

    ![workspace-4](../../../../translated_images/workspace-4.bac87f6599c4df63e624fc2608990f965887bee551d9dedc71c687b43b986b6a.tl.png)

   - I-click ang create + review at pagkatapos ay ang create button.
3. Hintayin na mabuo ang iyong workspace (maaari itong tumagal ng ilang minuto). Pagkatapos, pumunta dito sa portal. Maaari mo itong mahanap sa pamamagitan ng Machine Learning Azure service.
4. Sa Overview page ng iyong workspace, ilunsad ang Azure Machine Learning studio (o magbukas ng bagong browser tab at pumunta sa https://ml.azure.com), at mag-sign in sa Azure Machine Learning studio gamit ang iyong Microsoft account. Kung na-prompt, piliin ang iyong Azure directory at subscription, at ang iyong Azure Machine Learning workspace.
   
![workspace-5](../../../../translated_images/workspace-5.a6eb17e0a5e6420018b08bdaf3755ce977f96f1df3ea363d2476a9dce7e15adb.tl.png)

5. Sa Azure Machine Learning studio, i-toggle ang ☰ icon sa itaas na kaliwa upang makita ang iba't ibang pahina sa interface. Maaari mong gamitin ang mga pahinang ito upang pamahalaan ang mga resources sa iyong workspace.

![workspace-6](../../../../translated_images/workspace-6.8dd81fe841797ee17f8f73916769576260b16c4e17e850d277a49db35fd74a15.tl.png)

Maaari mong pamahalaan ang iyong workspace gamit ang Azure portal, ngunit para sa mga data scientist at Machine Learning operations engineers, ang Azure Machine Learning Studio ay nagbibigay ng mas nakatuon na user interface para sa pamamahala ng mga workspace resources.

### 2.2 Compute Resources

Ang Compute Resources ay mga cloud-based na resources kung saan maaari mong patakbuhin ang mga proseso ng model training at data exploration. Mayroong apat na uri ng compute resource na maaari mong likhain:

- **Compute Instances**: Mga development workstation na maaaring gamitin ng mga data scientist upang magtrabaho sa data at mga modelo. Kabilang dito ang paggawa ng Virtual Machine (VM) at paglulunsad ng notebook instance. Maaari kang magsanay ng modelo sa pamamagitan ng pagtawag sa compute cluster mula sa notebook.
- **Compute Clusters**: Mga scalable na cluster ng VMs para sa on-demand na pagproseso ng experiment code. Kakailanganin mo ito kapag nagsasanay ng modelo. Ang compute clusters ay maaari ring gumamit ng mga espesyal na GPU o CPU resources.
- **Inference Clusters**: Mga deployment target para sa predictive services na gumagamit ng iyong mga sinanay na modelo.
- **Attached Compute**: Nag-uugnay sa mga umiiral na Azure compute resources, tulad ng Virtual Machines o Azure Databricks clusters.

#### 2.2.1 Pagpili ng tamang opsyon para sa iyong compute resources

May ilang mahahalagang salik na dapat isaalang-alang kapag gumagawa ng compute resource, at ang mga pagpipiliang ito ay maaaring maging kritikal na desisyon.

**Kailangan mo ba ng CPU o GPU?**

Ang CPU (Central Processing Unit) ay ang electronic circuitry na nagpapatupad ng mga utos na bumubuo sa isang computer program. Ang GPU (Graphics Processing Unit) ay isang espesyal na electronic circuit na kayang magpatupad ng mga graphics-related code sa napakataas na bilis.

Ang pangunahing pagkakaiba ng CPU at GPU architecture ay ang CPU ay dinisenyo upang mabilis na mag-handle ng malawak na hanay ng mga gawain (nasusukat sa CPU clock speed), ngunit limitado ang kakayahan sa sabay-sabay na mga gawain. Ang GPUs ay dinisenyo para sa parallel computing kaya mas mahusay ito para sa mga deep learning tasks.

| CPU                                     | GPU                         |
|-----------------------------------------|-----------------------------|
| Mas mura                                | Mas mahal                  |
| Mas mababa ang concurrency              | Mas mataas ang concurrency |
| Mas mabagal sa pag-train ng deep learning models | Optimal para sa deep learning   |

**Laki ng Cluster**

Mas malalaking cluster ay mas mahal ngunit magreresulta sa mas mahusay na responsiveness. Kaya, kung may oras ka ngunit kulang sa pera, magsimula sa maliit na cluster. Sa kabaligtaran, kung may pera ka ngunit kulang sa oras, magsimula sa mas malaking cluster.

**Laki ng VM**

Depende sa iyong oras at budget, maaari mong baguhin ang laki ng RAM, disk, bilang ng cores, at clock speed. Ang pagtaas ng mga parameter na ito ay mas magastos ngunit magreresulta sa mas mahusay na performance.

**Dedicated o Low-Priority Instances?**

Ang low-priority instance ay nangangahulugang ito ay interruptible: sa esensya, maaaring kunin ng Microsoft Azure ang mga resources na ito at i-assign sa ibang gawain, kaya maaantala ang isang trabaho. Ang dedicated instance, o non-interruptible, ay nangangahulugang ang trabaho ay hindi kailanman matatapos nang walang iyong pahintulot. Isa itong konsiderasyon sa pagitan ng oras at pera, dahil ang interruptible instances ay mas mura kaysa sa dedicated ones.

#### 2.2.2 Paglikha ng compute cluster

Sa [Azure ML workspace](https://ml.azure.com/) na ginawa natin kanina, pumunta sa compute at makikita mo ang iba't ibang compute resources na tinalakay natin (i.e compute instances, compute clusters, inference clusters, at attached compute). Para sa proyektong ito, kakailanganin natin ng compute cluster para sa model training. Sa Studio, i-click ang "Compute" menu, pagkatapos ang "Compute cluster" tab, at i-click ang "+ New" button upang lumikha ng compute cluster.

![22](../../../../translated_images/cluster-1.b78cb630bb543729b11f60c34d97110a263f8c27b516ba4dc47807b3cee5579f.tl.png)

1. Piliin ang iyong mga opsyon: Dedicated vs Low priority, CPU o GPU, VM size, at core number (maaari mong panatilihin ang default settings para sa proyektong ito).
2. I-click ang Next button.

![23](../../../../translated_images/cluster-2.ea30cdbc9f926bb9e05af3fdbc1f679811c796dc2a6847f935290aec15526e88.tl.png)

3. Bigyan ang cluster ng compute name.  
4. Piliin ang iyong mga opsyon: Minimum/Maximum na bilang ng nodes, Idle seconds bago mag-scale down, SSH access. Tandaan na kung ang minimum na bilang ng nodes ay 0, makakatipid ka ng pera kapag idle ang cluster. Tandaan din na mas mataas ang bilang ng maximum nodes, mas maikli ang training. Ang maximum na bilang ng nodes na inirerekomenda ay 3.  
5. I-click ang "Create" button. Ang hakbang na ito ay maaaring tumagal ng ilang minuto.

![29](../../../../translated_images/cluster-3.8a334bc070ec173a329ce5abd2a9d727542e83eb2347676c9af20f2c8870b3e7.tl.png)

Ang galing! Ngayon na mayroon tayong Compute cluster, kailangan nating i-load ang data sa Azure ML Studio.

### 2.3 Paglo-load ng Dataset

1. Sa [Azure ML workspace](https://ml.azure.com/) na ginawa natin kanina, i-click ang "Datasets" sa kaliwang menu at i-click ang "+ Create dataset" button upang lumikha ng dataset. Piliin ang "From local files" na opsyon at piliin ang Kaggle dataset na na-download natin kanina.

   ![24](../../../../translated_images/dataset-1.e86ab4e10907a6e9c2a72577b51db35f13689cb33702337b8b7032f2ef76dac2.tl.png)

2. Bigyan ang iyong dataset ng pangalan, uri, at deskripsyon. I-click ang Next. I-upload ang data mula sa mga file. I-click ang Next.

   ![25](../../../../translated_images/dataset-2.f58de1c435d5bf9ccb16ccc5f5d4380eb2b50affca85cfbf4f97562bdab99f77.tl.png)

3. Sa Schema, baguhin ang data type sa Boolean para sa mga sumusunod na features: anaemia, diabetes, high blood pressure, sex, smoking, at DEATH_EVENT. I-click ang Next at pagkatapos ay i-click ang Create.

   ![26](../../../../translated_images/dataset-3.58db8c0eb783e89236a02bbce5bb4ba808d081a87d994d5284b1ae59928c95bf.tl.png)

Mahusay! Ngayon na ang dataset ay nasa lugar na at ang compute cluster ay nalikha, maaari na nating simulan ang pag-train ng modelo!

### 2.4 Low code/No Code training gamit ang AutoML

Ang tradisyunal na pagbuo ng machine learning model ay nangangailangan ng maraming resources, malalim na kaalaman, at oras upang makabuo at maikumpara ang dose-dosenang mga modelo.  
Ang Automated machine learning (AutoML) ay ang proseso ng pag-automate ng mga nakakaubos ng oras at paulit-ulit na gawain sa pagbuo ng machine learning model. Pinapayagan nito ang mga data scientist, analyst, at developer na bumuo ng ML models na may mataas na scale, kahusayan, at produktibidad, habang pinapanatili ang kalidad ng modelo. Binabawasan nito ang oras na kinakailangan upang makakuha ng production-ready ML models nang may kadalian at kahusayan. [Matuto pa](https://docs.microsoft.com/azure/machine-learning/concept-automated-ml?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109)

1. Sa [Azure ML workspace](https://ml.azure.com/) na ginawa natin kanina, i-click ang "Automated ML" sa kaliwang menu at piliin ang dataset na kakaupload mo lang. I-click ang Next.

   ![27](../../../../translated_images/aml-1.67281a85d3a1e2f34eb367b2d0f74e1039d13396e510f363cd8766632106d1ec.tl.png)

2. Maglagay ng bagong pangalan ng eksperimento, ang target column (DEATH_EVENT), at ang compute cluster na ginawa natin. I-click ang Next.

   ![28](../../../../translated_images/aml-2.c9fb9cffb39ccbbe21ab9810ae937195d41a489744e15cff2b8477ed4dcae1ec.tl.png)

3. Piliin ang "Classification" at i-click ang Finish. Ang hakbang na ito ay maaaring tumagal ng 30 minuto hanggang 1 oras, depende sa laki ng iyong compute cluster.

   ![30](../../../../translated_images/aml-3.a7952e4295f38cc6cdb0c7ed6dc71ea756b7fb5697ec126bc1220f87c5fa9231.tl.png)

4. Kapag natapos na ang run, i-click ang "Automated ML" tab, i-click ang iyong run, at i-click ang Algorithm sa "Best model summary" card.

   ![31](../../../../translated_images/aml-4.7a627e09cb6f16d0aa246059d9faee3d1725cc4258d0c8df15e801f73afc7e2c.tl.png)

Dito makikita mo ang detalyadong deskripsyon ng pinakamahusay na modelong nalikha ng AutoML. Maaari mo ring tuklasin ang iba pang mga modelo sa Models tab. Maglaan ng ilang minuto upang tuklasin ang mga modelo sa Explanations (preview button). Kapag napili mo na ang modelong nais mong gamitin (dito pipiliin natin ang pinakamahusay na modelo na pinili ng AutoML), titingnan natin kung paano ito ide-deploy.

## 3. Low code/No Code model deployment at endpoint consumption
### 3.1 Model deployment

Ang automated machine learning interface ay nagbibigay-daan sa iyo na i-deploy ang pinakamahusay na modelo bilang isang web service sa ilang hakbang. Ang deployment ay ang integrasyon ng modelo upang makagawa ito ng mga prediksyon batay sa bagong data at matukoy ang mga potensyal na oportunidad. Para sa proyektong ito, ang deployment sa isang web service ay nangangahulugang ang mga medical applications ay maaaring gumamit ng modelo upang makagawa ng live predictions ng panganib ng kanilang mga pasyente na magkaroon ng heart attack.

Sa deskripsyon ng pinakamahusay na modelo, i-click ang "Deploy" button.

![deploy-1](../../../../translated_images/deploy-1.ddad725acadc84e34553c3d09e727160faeb32527a9fb8b904c0f99235a34bb6.tl.png)

15. Bigyan ito ng pangalan, deskripsyon, compute type (Azure Container Instance), i-enable ang authentication, at i-click ang Deploy. Ang hakbang na ito ay maaaring tumagal ng humigit-kumulang 20 minuto upang makumpleto. Ang deployment process ay binubuo ng ilang hakbang kabilang ang pagrehistro ng modelo, pagbuo ng mga resources, at pag-configure ng mga ito para sa web service. Ang status message ay lilitaw sa ilalim ng Deploy status. Piliin ang Refresh nang pana-panahon upang suriin ang deployment status. Ito ay deployed at running kapag ang status ay "Healthy".

![deploy-2](../../../../translated_images/deploy-2.94dbb13f239086473aa4bf814342fd40483d136849b080f02bafbb995383940e.tl.png)

16. Kapag na-deploy na ito, i-click ang Endpoint tab at i-click ang endpoint na kakadeploy mo lang. Dito mo makikita ang lahat ng detalye na kailangan mong malaman tungkol sa endpoint.

![deploy-3](../../../../translated_images/deploy-3.fecefef070e8ef3b28e802326d107f61ac4e672d20bf82d05f78d025f9e6c611.tl.png)

Ang galing! Ngayon na mayroon tayong modelong na-deploy, maaari na nating simulan ang paggamit ng endpoint.

### 3.2 Endpoint consumption

I-click ang "Consume" tab. Dito mo makikita ang REST endpoint at isang python script sa consumption option. Maglaan ng oras upang basahin ang python code.

Ang script na ito ay maaaring patakbuhin nang direkta mula sa iyong lokal na makina at gagamitin ang iyong endpoint.

![35](../../../../translated_images/consumption-1.700abd196452842a020c7d745908637a6e4c5c50494ad1217be80e283e0de154.tl.png)

Maglaan ng oras upang suriin ang dalawang linyang ito ng code:

```python
url = 'http://98e3715f-xxxx-xxxx-xxxx-9ec22d57b796.centralus.azurecontainer.io/score'
api_key = '' # Replace this with the API key for the web service
```  
Ang `url` variable ay ang REST endpoint na matatagpuan sa consume tab at ang `api_key` variable ay ang primary key na matatagpuan din sa consume tab (kung sakaling na-enable mo ang authentication). Ganito magagamit ng script ang endpoint.

18. Kapag pinatakbo ang script, dapat mong makita ang sumusunod na output:  
    ```python
    b'"{\\"result\\": [true]}"'
    ```  
Ibig sabihin nito, ang prediksyon ng heart failure para sa ibinigay na data ay true. May lohika ito dahil kung titingnan mo nang mas malapit ang data na awtomatikong nalikha sa script, lahat ay nasa 0 at false bilang default. Maaari mong baguhin ang data gamit ang sumusunod na input sample:

```python
data = {
    "data":
    [
        {
            'age': "0",
            'anaemia': "false",
            'creatinine_phosphokinase': "0",
            'diabetes': "false",
            'ejection_fraction': "0",
            'high_blood_pressure': "false",
            'platelets': "0",
            'serum_creatinine': "0",
            'serum_sodium': "0",
            'sex': "false",
            'smoking': "false",
            'time': "0",
        },
        {
            'age': "60",
            'anaemia': "false",
            'creatinine_phosphokinase': "500",
            'diabetes': "false",
            'ejection_fraction': "38",
            'high_blood_pressure': "false",
            'platelets': "260000",
            'serum_creatinine': "1.40",
            'serum_sodium': "137",
            'sex': "false",
            'smoking': "false",
            'time': "130",
        },
    ],
}
```  
Ang script ay dapat magbalik ng:  
    ```python
    b'"{\\"result\\": [true, false]}"'
    ```  

Binabati kita! Ginamit mo lang ang modelong na-deploy at na-train sa Azure ML!

> **_NOTE:_** Kapag tapos ka na sa proyekto, huwag kalimutang i-delete ang lahat ng resources.

## 🚀 Hamon

Pag-aralan nang mabuti ang mga paliwanag at detalye ng modelo na nalikha ng AutoML para sa mga nangungunang modelo. Subukang intindihin kung bakit mas mahusay ang pinakamahusay na modelo kaysa sa iba. Anong mga algorithm ang ikinumpara? Ano ang mga pagkakaiba sa pagitan ng mga ito? Bakit mas mahusay ang performance ng pinakamahusay na modelo sa kasong ito?

## [Post-Lecture Quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/35)

## Review at Pag-aaral sa Sarili

Sa araling ito, natutunan mo kung paano mag-train, mag-deploy, at gumamit ng modelo upang mahulaan ang panganib ng heart failure sa isang Low code/No code na paraan sa cloud. Kung hindi mo pa nagagawa, masusing pag-aralan ang mga paliwanag ng modelo na nalikha ng AutoML para sa mga nangungunang modelo at subukang intindihin kung bakit mas mahusay ang pinakamahusay na modelo kaysa sa iba.

Maaari kang magpatuloy sa Low code/No code AutoML sa pamamagitan ng pagbabasa ng [dokumentasyon](https://docs.microsoft.com/azure/machine-learning/tutorial-first-experiment-automated-ml?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109).

## Takdang-Aralin

[Low code/No code Data Science project sa Azure ML](assignment.md)

---

**Paunawa**:  
Ang dokumentong ito ay isinalin gamit ang AI translation service na [Co-op Translator](https://github.com/Azure/co-op-translator). Bagama't sinisikap naming maging tumpak, pakatandaan na ang mga awtomatikong pagsasalin ay maaaring maglaman ng mga pagkakamali o hindi eksaktong salin. Ang orihinal na dokumento sa kanyang katutubong wika ang dapat ituring na opisyal na sanggunian. Para sa mahalagang impormasyon, inirerekomenda ang propesyonal na pagsasalin ng tao. Hindi kami mananagot sa anumang hindi pagkakaunawaan o maling interpretasyon na dulot ng paggamit ng pagsasaling ito.