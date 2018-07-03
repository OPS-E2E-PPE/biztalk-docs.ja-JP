---
title: API Management の SOAP エンドポイントを公開 |Microsoft Docs
description: 使用 Feature Pack 1 と Feature Pack 2 は、BizTalk の Wcf-basic HTTP の公開を API management 内の SOAP エンドポイントと場所が表示されます。 BizTalk 管理コンソールを使用して実行したり、Azure portal で API Management 内で直接、エンドポイントを貼り付けます。
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: 2
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: c8bdb3cb3f2d0fc247ea607a1b34623006315754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993715"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a><span data-ttu-id="8bc3d-104">API Management での BizTalk SOAP エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-104">Publish BizTalk SOAP endpoints in API Management</span></span>

<span data-ttu-id="8bc3d-105">Azure API Management 内のサービスと、BizTalk SOAP エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-105">Expose your BizTalk SOAP endpoints as services within Azure API Management.</span></span> 

<span data-ttu-id="8bc3d-106">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 1**、BizTalk から API Management で SOAP エンドポイントを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, you can expose a SOAP endpoint through API Management from BizTalk.</span></span> <span data-ttu-id="8bc3d-107">Azure portal で API Management を使用してこれが実行できます。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-107">You can do this using  API Management in the Azure portal.</span></span> 

<span data-ttu-id="8bc3d-108">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**Wcf-basichttp を公開する BizTalk 管理コンソールを使用して Azure API Management 内のエンドポイントと場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can expose a WCF-BasicHTTP receive location as an endpoint within Azure API Management using BizTalk Administration.</span></span> 

> [!TIP]
> <span data-ttu-id="8bc3d-109">[API Management とは何ですか。](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)優れたリソースを理解し、この Azure サービスの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-109">[What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) is a great resource to understand and learn more about this Azure service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8bc3d-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="8bc3d-110">Prerequisites</span></span>
* <span data-ttu-id="8bc3d-111">構成およびセットアップ[Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="8bc3d-111">Configure and set up [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="8bc3d-112">作成、[仮想ネットワーク](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと API Management インスタンスの間</span><span class="sxs-lookup"><span data-stu-id="8bc3d-112">Create a [virtual network](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) between your BizTalk computer and the API Management instance</span></span>
* <span data-ttu-id="8bc3d-113">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)を BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8bc3d-113">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on the BizTalk Server</span></span>

## <a name="create-using-api-management-in-azure-portal"></a><span data-ttu-id="8bc3d-114">Azure portal で API Management を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-114">Create using API Management in Azure portal</span></span> 
1. <span data-ttu-id="8bc3d-115">[Azure portal](https://portal.azure.com)を開いて、API management を選択します**Api**:</span><span class="sxs-lookup"><span data-stu-id="8bc3d-115">In the [Azure portal](https://portal.azure.com), open up your API management, and select **APIs**:</span></span>

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="8bc3d-117">選択**WSDL**:</span><span class="sxs-lookup"><span data-stu-id="8bc3d-117">Select **WSDL**:</span></span>

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="8bc3d-119">WSDL のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-119">Configure your WSDL properties:</span></span> 

   1. <span data-ttu-id="8bc3d-120">**WSDL 仕様**: BizTalk SOAP エンドポイントに完全な URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-120">**WSDL specification** : Enter the full URI to your BizTalk SOAP endpoint.</span></span> <span data-ttu-id="8bc3d-121">たとえば、ように入力します`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`または`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-121">For example, enter something like `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` or `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span></span>  

   2. <span data-ttu-id="8bc3d-122">**SOAP パススルー**または**SOAP REST から**: 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-122">**SOAP pass-through** or **SOAP to REST** : Select your preference:</span></span> 
       * <span data-ttu-id="8bc3d-123">**SOAP REST から**: 既存の (SOAP) ベースの web サービスからの HTTP Api の作成 (REST) ベース</span><span class="sxs-lookup"><span data-stu-id="8bc3d-123">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web service</span></span>
       * <span data-ttu-id="8bc3d-124">**SOAP パススルー**: SOAP API のプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-124">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

   3. <span data-ttu-id="8bc3d-125">優先入力**表示名**、**名前**、**説明**、 **API Url サフィックス**、**製品**、**バージョン**します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-125">Enter your preferred **Display Name**, **Name**, **Description**, **API Url suffix**, **Products**, and **Version**.</span></span>

      <span data-ttu-id="8bc3d-126">完了したら、WSDL 構成が、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-126">When finished, your WSDL configuration looks something like the following:</span></span> 

      ![BizTalk の WSDL から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="8bc3d-128">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-128">Select **Create**.</span></span>

## <a name="create-using-the-biztalk-administration"></a><span data-ttu-id="8bc3d-129">BizTalk 管理コンソールを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-129">Create using the BizTalk Administration</span></span>

> [!NOTE] 
> <span data-ttu-id="8bc3d-130">この機能をサポートする、Wcf-basichttp 受信場所。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-130">This feature is supported with WCF-BasicHTTP receive locations.</span></span> 

1. <span data-ttu-id="8bc3d-131">BizTalk 管理コンソールで、Wcf-basichttp 受信場所、および選択を右クリック**API Management に公開**:</span><span class="sxs-lookup"><span data-stu-id="8bc3d-131">In the BizTalk Administration Console, right-click your WCF-BasicHTTP receive location, and select **Publish to API Management**:</span></span>  

    ![[発行] メニュー オプション](../core/media/publish-to-api-management-option.png)
 
2. <span data-ttu-id="8bc3d-133">API 管理のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-133">Configure your API management properties:</span></span> 

   1. <span data-ttu-id="8bc3d-134">**サインイン**、Azure サブスクリプションを選択して、**サブスクリプション**と**リソース グループ**を持つ API management サービスであり、サービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-134">**Sign-in** to your Azure subscription, select the **Subscription** and **Resource Group** that has your API management service, and then select your service.</span></span>

   2. <span data-ttu-id="8bc3d-135">**WSDL 仕様リンク**WSDL ファイルが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-135">The **WSDL specification link** is automatically populated with your WSDL file.</span></span> <span data-ttu-id="8bc3d-136">置換**localhost** DNS 名または BizTalk Server の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-136">Replace **localhost** with the DNS name or IP address of the BizTalk Server.</span></span> 

   3. <span data-ttu-id="8bc3d-137">選択**SOAP パススルー**または**SOAP REST から**:</span><span class="sxs-lookup"><span data-stu-id="8bc3d-137">Select **SOAP pass-through** or **SOAP to REST**:</span></span>  
      * <span data-ttu-id="8bc3d-138">**SOAP REST から**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース</span><span class="sxs-lookup"><span data-stu-id="8bc3d-138">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web services</span></span>
      * <span data-ttu-id="8bc3d-139">**SOAP パススルー**: SOAP API のプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-139">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

        <span data-ttu-id="8bc3d-140">API 発行する両方の方法を変更して、 **API URL サフィックス**、し、さまざまな API の種類を使用して、発行します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-140">The API can be published both ways by changing the **API URL suffix**, and then publishing again using a different API type.</span></span>

   4. <span data-ttu-id="8bc3d-141">**API 名**受信場所の名前が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-141">The **API name** is automatically populated with the receive location name.</span></span>

   5. <span data-ttu-id="8bc3d-142">選択、 **API URL サフィックス**API のコンシューマーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-142">Select an **API URL suffix** that is to be used by consumers of the API.</span></span> 

      <span data-ttu-id="8bc3d-143">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-143">When finished, your properties look similar to the following:</span></span>  
      ![API ウィンドウへの公開します。](../core/media/api-management-publish-window.png)


3. <span data-ttu-id="8bc3d-145">選択**発行**します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-145">Select **Publish**.</span></span> <span data-ttu-id="8bc3d-146">内の API Management でサービスとして、受信場所が表示されます、成功すると、 [Azure portal](https://portal.azure.com)します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-146">When successful, the receive location is displayed as a service in API Management in the [Azure portal](https://portal.azure.com).</span></span> 

## <a name="do-more"></a><span data-ttu-id="8bc3d-147">さらに活用します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-147">Do more</span></span>
<span data-ttu-id="8bc3d-148">Azure API Management は、Logic Apps などの Azure サービスの多くで使用される強力なサービスです。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-148">Azure API Management is a powerful service that is used by a lot of Azure services, including Logic Apps.</span></span> <span data-ttu-id="8bc3d-149">API Management には、多くの機能、転送率の制限およびクォータは、独自の Api にアクセスできるユーザーを含む、キャッシュ、および詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-149">API Management includes many features, including rate limits and quotas, who has access to your APIs, caching, and more.</span></span> <span data-ttu-id="8bc3d-150">参照してください[API Management とは何ですか?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)を開始します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-150">See [What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) to get started.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bc3d-151">参照</span><span class="sxs-lookup"><span data-stu-id="8bc3d-151">See also</span></span>
[<span data-ttu-id="8bc3d-152">Feature Pack の構成</span><span class="sxs-lookup"><span data-stu-id="8bc3d-152">Configure the feature pack</span></span>](configure-the-feature-pack.md)
