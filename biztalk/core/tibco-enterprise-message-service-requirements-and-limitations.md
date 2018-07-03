---
title: TIBCO Enterprise Message Service の要件と制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453edabdadbd50b320a0bc078a638991ab7a3a5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995987"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="b6994-102">TIBCO Enterprise Message Service の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="b6994-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>

## <a name="system-requirements"></a><span data-ttu-id="b6994-103">システム要件</span><span class="sxs-lookup"><span data-stu-id="b6994-103">System Requirements</span></span>  
<span data-ttu-id="b6994-104">含まれている TIBCO Enterprise Message Service にはクライアント SDK (TIBCO EMS c# API を使用) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6994-104">Included with TIBCO Enterprise Message Service includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="b6994-105">BizTalk Adapter for TIBCO EMS は、この API を使用して TIBCO EMS とやり取りします。</span><span class="sxs-lookup"><span data-stu-id="b6994-105">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="add-the-api-to-the-gac"></a><span data-ttu-id="b6994-106">API を GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="b6994-106">Add the API to the GAC</span></span>  
 <span data-ttu-id="b6994-107">BizTalk Adapter for TIBCO EMS では、TIBCO EMS C# API である TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6994-107">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="b6994-108">このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="b6994-108">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1. <span data-ttu-id="b6994-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに TIBCO EMS C# API をコピーします。</span><span class="sxs-lookup"><span data-stu-id="b6994-109">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2. <span data-ttu-id="b6994-110">C# API ファイルである TIBCO.EMS.DLL の場所にディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="b6994-110">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
    <span data-ttu-id="b6994-111">既定のインストールでは、この DLL へのパスは c:\tibco\ems\clients\cs\TIBCO.EMS.DLL です。</span><span class="sxs-lookup"><span data-stu-id="b6994-111">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3. <span data-ttu-id="b6994-112">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6994-112">In a command prompt, type:</span></span>  
  
    `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
    <span data-ttu-id="b6994-113">TIBCO.EMS.dll に GAC が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6994-113">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
    <span data-ttu-id="b6994-114">コントロール パネルの [GAC の一覧を表示、開く**管理ツール**オープン**Microsoft .NET Framework x.xconfiguration]**、順にクリックします**アセンブリ キャッシュ**します。</span><span class="sxs-lookup"><span data-stu-id="b6994-114">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="b6994-115">制限事項</span><span class="sxs-lookup"><span data-stu-id="b6994-115">Limitations</span></span>  
 <span data-ttu-id="b6994-116">BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO.EMS.dll を使用して TIBCO Enterprise Message Service とやり取りします。</span><span class="sxs-lookup"><span data-stu-id="b6994-116">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="b6994-117">TIBCO EMS C# API を使用するときは、次の制限事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6994-117">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="b6994-118">この C# API では、メッセージ圧縮 (TIBCO EMS クライアントが EMS に圧縮形式でメッセージを送信できるようにします) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b6994-118">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="b6994-119">この C# API では、アダプターとサーバーの間でメッセージを暗号化することはできません。</span><span class="sxs-lookup"><span data-stu-id="b6994-119">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="b6994-120">この C# API では、OpenSSL ライブラリを使用した SSL 暗号化は許可されません。</span><span class="sxs-lookup"><span data-stu-id="b6994-120">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="b6994-121">この C# API は、EMS 用の管理 API をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="b6994-121">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="b6994-122">BizTalk TIBCO EMS アダプターを使用して、50 MB を超えるサイズのメッセージを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="b6994-122">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="b6994-123">このサイズを超えた場合、System.OutOfMemoryException 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="b6994-123">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6994-124">参照</span><span class="sxs-lookup"><span data-stu-id="b6994-124">See Also</span></span>  
 [<span data-ttu-id="b6994-125">計画および設計</span><span class="sxs-lookup"><span data-stu-id="b6994-125">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)