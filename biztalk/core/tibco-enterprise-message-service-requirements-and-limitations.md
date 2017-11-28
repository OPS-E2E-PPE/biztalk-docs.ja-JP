---
title: "TIBCO Enterprise Message Service の要件と制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption
- messages, compression
- EMS limitations
- message compression
- API, adding to GAC
- global assembly cache, adding API
- GAC, adding TIBCO EMS API
- system requirements
- TIBCO.EMS.dll
- EMS requirements
- messages, encryption
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e49f4a74cce4414fd9d0b069a382d9facb03d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="e5d78-102">TIBCO Enterprise Message Service の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="e5d78-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>
## <a name="system-requirements"></a><span data-ttu-id="e5d78-103">システム要件</span><span class="sxs-lookup"><span data-stu-id="e5d78-103">System Requirements</span></span>  
 <span data-ttu-id="e5d78-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO Enterprise Message Service (EMS) バージョン 4.2 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e5d78-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service supports TIBCO Enterprise Message Service (EMS) version 4.2.</span></span> <span data-ttu-id="e5d78-105">TIBCO EMS バージョン 4.2 には、クライアント SDK (TIBCO EMS C# API を使用) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5d78-105">Included with TIBCO EMS version 4.2 is a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="e5d78-106">BizTalk Adapter for TIBCO EMS は、この API を使用して TIBCO EMS とやり取りします。</span><span class="sxs-lookup"><span data-stu-id="e5d78-106">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="adding-the-api-to-the-gac"></a><span data-ttu-id="e5d78-107">GAC への API の追加</span><span class="sxs-lookup"><span data-stu-id="e5d78-107">Adding the API to the GAC</span></span>  
 <span data-ttu-id="e5d78-108">BizTalk Adapter for TIBCO EMS では、TIBCO EMS C# API である TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d78-108">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="e5d78-109">このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="e5d78-109">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
#### <a name="to-add-the-tibco-ems-c-api-to-the-gac"></a><span data-ttu-id="e5d78-110">TIBCO EMS c# API を GAC に追加するには</span><span class="sxs-lookup"><span data-stu-id="e5d78-110">To add the TIBCO EMS C# API to the GAC</span></span>  
  
1.  <span data-ttu-id="e5d78-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに TIBCO EMS C# API をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e5d78-111">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2.  <span data-ttu-id="e5d78-112">C# API ファイルである TIBCO.EMS.DLL の場所にディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="e5d78-112">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
     <span data-ttu-id="e5d78-113">既定のインストールでは、この DLL へのパスは c:\tibco\ems\clients\cs\TIBCO.EMS.DLL です。</span><span class="sxs-lookup"><span data-stu-id="e5d78-113">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3.  <span data-ttu-id="e5d78-114">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e5d78-114">In a command prompt, type:</span></span>  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     <span data-ttu-id="e5d78-115">TIBCO.EMS.dll に GAC が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e5d78-115">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
     <span data-ttu-id="e5d78-116">コントロール パネルの [GAC の一覧を表示、開く**管理ツール**、開かれている**Microsoft .NET Framework x.xconfiguration]**、クリックして**アセンブリ キャッシュ**です。</span><span class="sxs-lookup"><span data-stu-id="e5d78-116">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="e5d78-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="e5d78-117">Limitations</span></span>  
 <span data-ttu-id="e5d78-118">BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO.EMS.dll を使用して TIBCO Enterprise Message Service とやり取りします。</span><span class="sxs-lookup"><span data-stu-id="e5d78-118">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="e5d78-119">TIBCO EMS C# API を使用するときは、次の制限事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d78-119">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="e5d78-120">この C# API では、メッセージ圧縮 (TIBCO EMS クライアントが EMS に圧縮形式でメッセージを送信できるようにします) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5d78-120">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="e5d78-121">この C# API では、アダプターとサーバーの間でメッセージを暗号化することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5d78-121">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="e5d78-122">この C# API では、OpenSSL ライブラリを使用した SSL 暗号化は許可されません。</span><span class="sxs-lookup"><span data-stu-id="e5d78-122">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="e5d78-123">この C# API は、EMS 用の管理 API をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e5d78-123">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="e5d78-124">BizTalk TIBCO EMS アダプターを使用して、50 MB を超えるサイズのメッセージを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5d78-124">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="e5d78-125">このサイズを超えた場合、System.OutOfMemoryException 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e5d78-125">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d78-126">参照</span><span class="sxs-lookup"><span data-stu-id="e5d78-126">See Also</span></span>  
 [<span data-ttu-id="e5d78-127">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e5d78-127">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)