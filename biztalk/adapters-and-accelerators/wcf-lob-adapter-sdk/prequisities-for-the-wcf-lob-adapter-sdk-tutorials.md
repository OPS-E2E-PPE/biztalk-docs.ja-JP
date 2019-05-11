---
title: WCF LOB Adapter SDK のチュートリアルの Prequisities |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d47ac1-1605-4c6d-a331-8583771dca28
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 454b2465072ed6cbdb19a1ac6b7cdae672698aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363401"
---
# <a name="prequisities-for-the-wcf-lob-adapter-sdk-tutorials"></a><span data-ttu-id="b535c-102">WCF LOB Adapter SDK のチュートリアルの Prequisities</span><span class="sxs-lookup"><span data-stu-id="b535c-102">Prequisities for the WCF LOB Adapter SDK tutorials</span></span>
<span data-ttu-id="b535c-103">このセクションでは、それらを完了するために必要なソフトウェアと同様に、チュートリアルを最大限に慣れておく必要がある概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="b535c-103">This section provides details about the concepts you should be familiar with to get the most out of the tutorials, as well as the software required to complete them.</span></span>  
  
## <a name="what-to-install"></a><span data-ttu-id="b535c-104">インストールします。</span><span class="sxs-lookup"><span data-stu-id="b535c-104">What to Install</span></span>  
 <span data-ttu-id="b535c-105">チュートリアルを開始するには、コンピューターにインストールされている、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="b535c-105">To start the tutorials, you must have the following software installed on your computer.</span></span>  
  
- [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]
  
- <span data-ttu-id="b535c-106">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="b535c-106">Internet Information Services (IIS)</span></span>  
  
- [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]
  
- [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] <span data-ttu-id="b535c-107">(BizTalk Server インストール ファイル、および名前付き ASDK_x64 と ASDK_x86 で使用可能)</span><span class="sxs-lookup"><span data-stu-id="b535c-107">(available with your BizTalk Server installation files, and named ASDK_x64 and ASDK_x86)</span></span>  
  
  <span data-ttu-id="b535c-108">チュートリアル 3 を完了するには、コンピューターにインストールされている、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="b535c-108">To complete Tutorial 3, you must have the following software installed on your computer.</span></span>  
  
- <span data-ttu-id="b535c-109">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="b535c-109">Microsoft SharePoint</span></span>  
  
- <span data-ttu-id="b535c-110">Microsoft SharePoint SDK</span><span class="sxs-lookup"><span data-stu-id="b535c-110">Microsoft SharePoint SDK</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b535c-111">実稼働環境では、これらのチュートリアルを実行しません。</span><span class="sxs-lookup"><span data-stu-id="b535c-111">Do not perform these tutorials in your production environment.</span></span>  
  
<span data-ttu-id="b535c-112">完了したエコー アダプターので、BizTalk のインストール ファイルに含まれている`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`します。</span><span class="sxs-lookup"><span data-stu-id="b535c-112">The completed Echo Adapter is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b535c-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="b535c-113">Prerequisites</span></span>  
 <span data-ttu-id="b535c-114">チュートリアルでは、次のようにについて理解しているものとします。</span><span class="sxs-lookup"><span data-stu-id="b535c-114">The tutorials assume that you are familiar with the following:</span></span>  
  
- <span data-ttu-id="b535c-115">オブジェクト指向のソフトウェアの設計と開発</span><span class="sxs-lookup"><span data-stu-id="b535c-115">Object-oriented software design and development</span></span>  
  
- <span data-ttu-id="b535c-116">Windows Communication Foundation (WCF) は、具体的には、モデルのプログラミングのチャネルし、モデルのプログラミングをサービス</span><span class="sxs-lookup"><span data-stu-id="b535c-116">Windows Communication Foundation (WCF), specifically, channel model programming and service model programming</span></span>  
  
- <span data-ttu-id="b535c-117">XSD、XML、WSDL、および Web サービス記述言語 (WSDL) と API 間のリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="b535c-117">XSD, XML, WSDL, and the relationship between Web Services Description Language (WSDL) and an API</span></span>  
  
- <span data-ttu-id="b535c-118">C# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="b535c-118">C# programming language</span></span>  
  
- <span data-ttu-id="b535c-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b535c-119">.NET Framework</span></span>  
  
  <span data-ttu-id="b535c-120">チュートリアルを開始する前にことが便利な場合は、この SDK の概念説明のトピックを確認し、チャネルでの基本的な知識がある[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、内の型を含む、 **T:Microsoft.ServiceModel.Channels**と**T:Microsoft.ServiceModel.Channels.Common**名前空間。</span><span class="sxs-lookup"><span data-stu-id="b535c-120">Before starting the tutorials, it will be helpful if you have reviewed the conceptual topics of this SDK, and have a general understanding of channels in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], including the types within the **T:Microsoft.ServiceModel.Channels** and **T:Microsoft.ServiceModel.Channels.Common** namespaces.</span></span>  <span data-ttu-id="b535c-121">チャネルの詳細については、次を参照してください。、[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="b535c-121">For more information about channels, see the [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b535c-122">参照</span><span class="sxs-lookup"><span data-stu-id="b535c-122">See Also</span></span>  
 [<span data-ttu-id="b535c-123">WCF LOB Adapter SDK についてのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="b535c-123">Tutorials to learn the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)