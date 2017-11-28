---
title: "API Management の SOAP エンドポイントを公開 |Microsoft ドキュメント"
description: "BizTalk Wcf-basic HTTP を公開するには、使用する機能パック 1 および Feature Pack 2 は、API management 内で SOAP エンドポイントと場所を受信します。 BizTalk 管理コンソールを使用してこれを行うか、Azure ポータルで API Management 内で直接、エンドポイントを貼り付けますことができます。"
ms.custom: 
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: 8ac1e824ad11ef18eac6deb1252101bbd1ec187a
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a><span data-ttu-id="236e5-104">API Management で BizTalk SOAP エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="236e5-104">Publish BizTalk SOAP endpoints in API Management</span></span>

<span data-ttu-id="236e5-105">Azure API Management 内でサービスとして、BizTalk SOAP エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="236e5-105">Expose your BizTalk SOAP endpoints as services within Azure API Management.</span></span> 

<span data-ttu-id="236e5-106">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 1**、API Management BizTalk からによって SOAP エンドポイントを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="236e5-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, you can expose a SOAP endpoint through API Management from BizTalk.</span></span> <span data-ttu-id="236e5-107">これを行う、Azure ポータルで API Management を使用します。</span><span class="sxs-lookup"><span data-stu-id="236e5-107">You can do this using  API Management in the Azure portal.</span></span> 

<span data-ttu-id="236e5-108">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**Wcf-basichttp を公開する BizTalk 管理コンソールを使用して Azure API Management 内のエンドポイントと場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="236e5-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can expose a WCF-BasicHTTP receive location as an endpoint within Azure API Management using BizTalk Administration.</span></span> 

> [!TIP]
> <span data-ttu-id="236e5-109">[API Management とは何ですか。](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts)を理解し、Azure サービスに関する詳細については、優れたリソースです。</span><span class="sxs-lookup"><span data-stu-id="236e5-109">[What is API Management?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) is a great resource to understand and learn more about this Azure service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="236e5-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="236e5-110">Prerequisites</span></span>
* <span data-ttu-id="236e5-111">構成およびセットアップ[Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="236e5-111">Configure and set up [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="236e5-112">作成、[仮想ネットワーク](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと、API Management インスタンス間で</span><span class="sxs-lookup"><span data-stu-id="236e5-112">Create a [virtual network](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) between your BizTalk computer and the API Management instance</span></span>
* <span data-ttu-id="236e5-113">インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で</span><span class="sxs-lookup"><span data-stu-id="236e5-113">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on the BizTalk Server</span></span>

## <a name="create-using-api-management-in-azure-portal"></a><span data-ttu-id="236e5-114">Azure ポータルで API Management を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="236e5-114">Create using API Management in Azure portal</span></span> 
1. <span data-ttu-id="236e5-115">[Azure ポータル](https://portal.azure.com)、API 管理を開くし、選択、 **Api**:</span><span class="sxs-lookup"><span data-stu-id="236e5-115">In the [Azure portal](https://portal.azure.com), open up your API management, and select **APIs**:</span></span>

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="236e5-117">選択**WSDL**:</span><span class="sxs-lookup"><span data-stu-id="236e5-117">Select **WSDL**:</span></span>

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="236e5-119">WSDL のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="236e5-119">Configure your WSDL properties:</span></span> 

    1. <span data-ttu-id="236e5-120">**WSDL 仕様**: から BizTalk SOAP エンドポイントへの完全 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="236e5-120">**WSDL specification** : Enter the full URI to your BizTalk SOAP endpoint.</span></span> <span data-ttu-id="236e5-121">たとえば、ように入力`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`または`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`です。</span><span class="sxs-lookup"><span data-stu-id="236e5-121">For example, enter something like `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` or `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span></span>  

    2. <span data-ttu-id="236e5-122">**SOAP パススルー**または**他の部分 SOAP** : 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="236e5-122">**SOAP pass-through** or **SOAP to REST** : Select your preference:</span></span> 
        * <span data-ttu-id="236e5-123">**他の部分 SOAP**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース</span><span class="sxs-lookup"><span data-stu-id="236e5-123">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web service</span></span>
        * <span data-ttu-id="236e5-124">**SOAP パススルー**: SOAP API のプロキシとして機能</span><span class="sxs-lookup"><span data-stu-id="236e5-124">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

    3. <span data-ttu-id="236e5-125">優先入力**表示名**、**名前**、**説明**、 **API Url サフィックス**、**製品**、および**バージョン**します。</span><span class="sxs-lookup"><span data-stu-id="236e5-125">Enter your preferred **Display Name**, **Name**, **Description**, **API Url suffix**, **Products**, and **Version**.</span></span>

    <span data-ttu-id="236e5-126">完了したら、WSDL 構成のようになります次。</span><span class="sxs-lookup"><span data-stu-id="236e5-126">When finished, your WSDL configuration looks something like the following:</span></span> 

    ![WSDL BizTalk から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="236e5-128">**[作成]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="236e5-128">Select **Create**.</span></span>

## <a name="create-using-the-biztalk-administration"></a><span data-ttu-id="236e5-129">BizTalk 管理コンソールを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="236e5-129">Create using the BizTalk Administration</span></span>

> [!NOTE] 
> <span data-ttu-id="236e5-130">この機能をサポートする、Wcf-basichttp 受信場所。</span><span class="sxs-lookup"><span data-stu-id="236e5-130">This feature is supported with WCF-BasicHTTP receive locations.</span></span> 

1. <span data-ttu-id="236e5-131">BizTalk 管理コンソールで、右クリックして、Wcf-basichttp 受信場所、および選択**API Management に発行**:</span><span class="sxs-lookup"><span data-stu-id="236e5-131">In the BizTalk Administration Console, right-click your WCF-BasicHTTP receive location, and select **Publish to API Management**:</span></span>  

    ![パブリッシュ メニュー オプション](../core/media/publish-to-api-management-option.png)
 
2. <span data-ttu-id="236e5-133">API 管理のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="236e5-133">Configure your API management properties:</span></span> 

    1. <span data-ttu-id="236e5-134">**サイン イン**、Azure サブスクリプションを選択して、**サブスクリプション**と**リソース グループ**を持つ、API management サービスであり、サービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="236e5-134">**Sign-in** to your Azure subscription, select the **Subscription** and **Resource Group** that has your API management service, and then select your service.</span></span>

    2. <span data-ttu-id="236e5-135">**WSDL 仕様リンク**WSDL ファイルが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="236e5-135">The **WSDL specification link** is automatically populated with your WSDL file.</span></span> <span data-ttu-id="236e5-136">置き換える**localhost** DNS 名または BizTalk Server の IP アドレスでします。</span><span class="sxs-lookup"><span data-stu-id="236e5-136">Replace **localhost** with the DNS name or IP address of the BizTalk Server.</span></span> 

    3. <span data-ttu-id="236e5-137">選択**SOAP パススルー**または**他の部分 SOAP**:</span><span class="sxs-lookup"><span data-stu-id="236e5-137">Select **SOAP pass-through** or **SOAP to REST**:</span></span>  
        * <span data-ttu-id="236e5-138">**他の部分 SOAP**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース</span><span class="sxs-lookup"><span data-stu-id="236e5-138">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web services</span></span>
        * <span data-ttu-id="236e5-139">**SOAP パススルー**: SOAP API のプロキシとして機能</span><span class="sxs-lookup"><span data-stu-id="236e5-139">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

        <span data-ttu-id="236e5-140">API によって発行できます両方の方法を変更する、 **API URL サフィックス**、し、これは、各種の API を使ってもう一度発行します。</span><span class="sxs-lookup"><span data-stu-id="236e5-140">The API can be published both ways by changing the **API URL suffix**, and then publishing again using a different API type.</span></span>

    4. <span data-ttu-id="236e5-141">**API 名**受信場所の名前が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="236e5-141">The **API name** is automatically populated with the receive location name.</span></span>

    5. <span data-ttu-id="236e5-142">選択、 **API URL サフィックス**API のコンシューマーによって使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="236e5-142">Select an **API URL suffix** that is to be used by consumers of the API.</span></span> 

    <span data-ttu-id="236e5-143">完了したらのプロパティが、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="236e5-143">When finished, your properties look similar to the following:</span></span>  
    ![API ウィンドウへの公開します。](../core/media/api-management-publish-window.png)


3. <span data-ttu-id="236e5-145">選択**発行**です。</span><span class="sxs-lookup"><span data-stu-id="236e5-145">Select **Publish**.</span></span> <span data-ttu-id="236e5-146">成功すると、受信場所が表示されますで API Management でサービスとして、 [Azure ポータル](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="236e5-146">When successful, the receive location is displayed as a service in API Management in the [Azure portal](https://portal.azure.com).</span></span> 

## <a name="do-more"></a><span data-ttu-id="236e5-147">複数の操作を行います</span><span class="sxs-lookup"><span data-stu-id="236e5-147">Do more</span></span>
<span data-ttu-id="236e5-148">Azure API Management とは、多数の Logic Apps を含む、Azure のサービスによって使用される強力なサービスです。</span><span class="sxs-lookup"><span data-stu-id="236e5-148">Azure API Management is a powerful service that is used by a lot of Azure services, including Logic Apps.</span></span> <span data-ttu-id="236e5-149">API Management には、多くの機能、転送率の制限、クォータ、独自の Api へのアクセスを持つなど、キャッシュ、および詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="236e5-149">API Management includes many features, including rate limits and quotas, who has access to your APIs, caching, and more.</span></span> <span data-ttu-id="236e5-150">参照してください[API Management は何ですか?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts)作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="236e5-150">See [What is API Management?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) to get started.</span></span>

## <a name="see-also"></a><span data-ttu-id="236e5-151">参照</span><span class="sxs-lookup"><span data-stu-id="236e5-151">See also</span></span>
[<span data-ttu-id="236e5-152">Feature Pack の構成</span><span class="sxs-lookup"><span data-stu-id="236e5-152">Configure the feature pack</span></span>](configure-the-feature-pack.md)
