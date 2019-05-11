---
title: BizTalk adapter 用 Siebel eBusiness Applications の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16d62607a1c970b0d391a8077da4ddecb8d86160
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371285"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="89b40-102">BizTalk adapter 用 Siebel eBusiness Applications の概要</span><span class="sxs-lookup"><span data-stu-id="89b40-102">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="89b40-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] WCF サービスとしての Siebel システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="89b40-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes the Siebel system as a WCF service.</span></span> <span data-ttu-id="89b40-104">アダプターのクライアントは、アダプターを使用した SOAP メッセージを交換することで Siebel システムの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="89b40-104">Adapter clients can perform operations on the Siebel system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="89b40-105">アダプターは WCF メッセージを使用し、操作を実行する Siebel システムへの適切な呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="89b40-105">The adapter consumes the WCF message and makes appropriate calls to the Siebel system to perform the operation.</span></span> <span data-ttu-id="89b40-106">アダプターは、Siebel システムから SOAP メッセージの形式でクライアントに応答を返します。</span><span class="sxs-lookup"><span data-stu-id="89b40-106">The adapter returns the response from the Siebel system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="89b40-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WSDL の形式でメッセージの SOAP の構造を記述する Siebel の成果物 (ビジネス コンポーネント、ビジネス サービス) のサーフェスのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="89b40-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces metadata of Siebel artifacts (business components, business services) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="89b40-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]と[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。</span><span class="sxs-lookup"><span data-stu-id="89b40-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="89b40-109">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムにアクセスする Siebel COM のデータ コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="89b40-109">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the Siebel COM Data Control to access the Siebel system.</span></span> <span data-ttu-id="89b40-110">Siebel COM のデータ コントロールは、Siebel Web クライアントに付属します。</span><span class="sxs-lookup"><span data-stu-id="89b40-110">The Siebel COM Data Control comes bundled with the Siebel Web client.</span></span> <span data-ttu-id="89b40-111">そのため、Siebel Web クライアントと同じコンピューターにインストールされているがであることを確認、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="89b40-111">Hence, make sure you have the Siebel Web client installed on the same computer as the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="89b40-112">使用することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]次の方法で Siebel システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="89b40-112">You can use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to communicate with the Siebel system in the following ways:</span></span>  
  
-   <span data-ttu-id="89b40-113">BizTalk アプリケーションを開発しています。</span><span class="sxs-lookup"><span data-stu-id="89b40-113">By developing BizTalk applications.</span></span> <span data-ttu-id="89b40-114">参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="89b40-114">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md).</span></span>
  
-   <span data-ttu-id="89b40-115">WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="89b40-115">By using the WCF service model.</span></span> <span data-ttu-id="89b40-116">参照してください[WCF サービス モデルを使用して Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="89b40-116">See [Develop Siebel Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="89b40-117">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="89b40-117">By using the WCF channel model.</span></span> <span data-ttu-id="89b40-118">WCF チャネル モデルを使用して Oracle データベース アプリケーションの開発を参照してください[ここリンクの説明を入力](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="89b40-118">See Develop Oracle Database Applications by Using the WCF Channel Model[enter link description here](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89b40-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89b40-119">In This Section</span></span>  
  
-   <span data-ttu-id="89b40-120">[アダプターは、Siebel システムにどのように接続しますか。](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="89b40-120">[How Does the Adapter Connect to a Siebel System?](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="89b40-121">[アダプターのサーフェス Siebel メタデータのしくみですか。](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="89b40-121">[How Does the Adapter Surface Siebel Metadata?](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="89b40-122">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="89b40-122">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="89b40-123">[アダプターでサポートされているその他の機能](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="89b40-123">[Other Features Supported by the Adapter](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="89b40-124">参照</span><span class="sxs-lookup"><span data-stu-id="89b40-124">See Also</span></span>  
 [<span data-ttu-id="89b40-125">BizTalk Adapter for Siebel eBusiness Applications について</span><span class="sxs-lookup"><span data-stu-id="89b40-125">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)