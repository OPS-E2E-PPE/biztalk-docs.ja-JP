---
title: "BizTalk Server を使用して Azure API Management への接続 |Microsoft ドキュメント"
description: "BizTalk 機能パック 1 を使用して、BizTalk Server から API management に接続するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d0c5e4cd2a0ebbd7108845ea15de468d0e0a5a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-azure-api-management"></a><span data-ttu-id="f23f0-103">Azure API Management への接続します。</span><span class="sxs-lookup"><span data-stu-id="f23f0-103">Connect to Azure API Management</span></span>
<span data-ttu-id="f23f0-104">ここで BizTalk から API 管理により、SOAP エンドポイントを簡単に公開できます。</span><span class="sxs-lookup"><span data-stu-id="f23f0-104">You can now easily expose your SOAP endpoint through API Management from BizTalk.</span></span>

## <a name="what-is-azure-api-management"></a><span data-ttu-id="f23f0-105">Azure API Management とは</span><span class="sxs-lookup"><span data-stu-id="f23f0-105">What is Azure API Management</span></span>
<span data-ttu-id="f23f0-106">内部および外部の顧客に Api を公開するため、ターンキー ソリューションとして Azure API Management を使用します。</span><span class="sxs-lookup"><span data-stu-id="f23f0-106">Use Azure API Management as a turnkey solution for publishing APIs to external and internal customers.</span></span> <span data-ttu-id="f23f0-107">一貫性をすばやく作成し、どこにでもホストされている既存のバックエンド サービスの最新の API ゲートウェイをセキュリティで保護使いすぎ、不正使用から保護すると、使用状況と正常性に関する洞察を取得します。</span><span class="sxs-lookup"><span data-stu-id="f23f0-107">Quickly create consistent and modern API gateways for existing back-end services hosted anywhere, secure and protect them from abuse and overuse, and get insights into usage and health.</span></span> <span data-ttu-id="f23f0-108">さらに、自動化し、API プログラムを準備して稼働させるために、開発者のオンボーディングを拡張します。</span><span class="sxs-lookup"><span data-stu-id="f23f0-108">Plus, automate and scale developer onboarding to help get your API program up and running.</span></span> 

<span data-ttu-id="f23f0-109">参照してください[API Management](https://azure.microsoft.com/en-us/services/api-management/)を API Management の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23f0-109">See [API Management](https://azure.microsoft.com/en-us/services/api-management/) to learn more about API Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f23f0-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="f23f0-110">Prerequisites</span></span>
* <span data-ttu-id="f23f0-111">構成およびセットアップ[Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="f23f0-111">Configure and set up [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="f23f0-112">作成、[仮想ネットワーク](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと API 管理インスタンス間で</span><span class="sxs-lookup"><span data-stu-id="f23f0-112">Create a [virtual network](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet) between your BizTalk Machine and the API Managemenet instance</span></span>


1. <span data-ttu-id="f23f0-113">Azure ポータルで、API management を開き、選択**Api**  メニューから。</span><span class="sxs-lookup"><span data-stu-id="f23f0-113">In the Azure portal, open up your API management, and select **APIs** from the menu:</span></span>

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="f23f0-115">オプションを選択**WSDL**新しい API セクション。</span><span class="sxs-lookup"><span data-stu-id="f23f0-115">Select the option for **WSDL** in the New API section:</span></span>

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="f23f0-117">BizTalk の WSDL に API Management に接続するには、SOAP エンドポイントへの完全 URI での BizTalk コンピューターに対する URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="f23f0-117">To connect to API Management to your BizTalk WSDL, copy the URL to your BizTalk computer with the full URI to your SOAP endpoint.</span></span> <span data-ttu-id="f23f0-118">たとえば、コピー `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span><span class="sxs-lookup"><span data-stu-id="f23f0-118">For example, copy `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span></span>

    ![WSDL BizTalk から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="f23f0-120">使用する場合に選択、 **SOAP パススルー**、設定、または、**他の部分 SOAP**サービス。</span><span class="sxs-lookup"><span data-stu-id="f23f0-120">Select if you want to use a **SOAP pass-through**, or set up a **SOAP to REST** service.</span></span>
5. <span data-ttu-id="f23f0-121">入力してください、**名前**、API の**説明**、および**API Url サフィックス**サービス用です。</span><span class="sxs-lookup"><span data-stu-id="f23f0-121">Enter the **name** of your API, the **Description**, and the **API Url suffix** for your service.</span></span>
6. <span data-ttu-id="f23f0-122">選択**作成**バックエンドの SOAP エンドポイントへの通信を作成します。</span><span class="sxs-lookup"><span data-stu-id="f23f0-122">Select **Create** to create the communication to your backend SOAP endpoint.</span></span>

## <a name="see-also"></a><span data-ttu-id="f23f0-123">参照</span><span class="sxs-lookup"><span data-stu-id="f23f0-123">See also</span></span>
[<span data-ttu-id="f23f0-124">Feature Pack の構成</span><span class="sxs-lookup"><span data-stu-id="f23f0-124">Configure the feature pack</span></span>](configure-the-feature-pack.md)