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
ms.openlocfilehash: 94a0adbc67dfb78eef97876d65b4da50a343efce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379842"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="31d94-102">TIBCO Enterprise Message Service の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="31d94-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>

## <a name="system-requirements"></a><span data-ttu-id="31d94-103">システム要件</span><span class="sxs-lookup"><span data-stu-id="31d94-103">System Requirements</span></span>  
<span data-ttu-id="31d94-104">含まれている TIBCO Enterprise Message Service にはクライアント SDK (TIBCO EMS c# API を使用) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31d94-104">Included with TIBCO Enterprise Message Service includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="31d94-105">BizTalk Adapter for TIBCO EMS では、この API を使用して、TIBCO EMS と通信します。</span><span class="sxs-lookup"><span data-stu-id="31d94-105">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="add-the-api-to-the-gac"></a><span data-ttu-id="31d94-106">API を GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="31d94-106">Add the API to the GAC</span></span>  
 <span data-ttu-id="31d94-107">BizTalk Adapter for TIBCO EMS は、TIBCO EMS を必要とC#API, TIBCO します。EMS.dll、グローバル アセンブリ キャッシュ (GAC) に追加します。</span><span class="sxs-lookup"><span data-stu-id="31d94-107">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="31d94-108">アダプターは、例外をトリガーし、このアセンブリがインストールされていない場合、適切なメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="31d94-108">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1. <span data-ttu-id="31d94-109">コピーに TIBCO EMS C# #API、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="31d94-109">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2. <span data-ttu-id="31d94-110">ディレクトリの場所を変更、 C# API ファイルで TIBCO します。EMS します。DLL です。</span><span class="sxs-lookup"><span data-stu-id="31d94-110">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
    <span data-ttu-id="31d94-111">既定のインストールでは、この DLL へのパスは、c:\tibco\ems\clients\cs\TIBCO が。EMS します。DLL です。</span><span class="sxs-lookup"><span data-stu-id="31d94-111">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3. <span data-ttu-id="31d94-112">コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="31d94-112">In a command prompt, type:</span></span>  
  
    `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
    <span data-ttu-id="31d94-113">TIBCO します。EMS.dll GAC が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="31d94-113">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
    <span data-ttu-id="31d94-114">コントロール パネルの [GAC の一覧を表示、開く**管理ツール**オープン**Microsoft .NET Framework x.xconfiguration]**、順にクリックします**アセンブリ キャッシュ**します。</span><span class="sxs-lookup"><span data-stu-id="31d94-114">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="31d94-115">制限事項</span><span class="sxs-lookup"><span data-stu-id="31d94-115">Limitations</span></span>  
 <span data-ttu-id="31d94-116">BizTalk Adapter for TIBCO Enterprise Message Service は、TIBCO を使用します。TIBCO Enterprise Message Service との通信に EMS.dll します。</span><span class="sxs-lookup"><span data-stu-id="31d94-116">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="31d94-117">TIBCO EMS を使用すると、次の制限を考慮する必要がありますC#API:</span><span class="sxs-lookup"><span data-stu-id="31d94-117">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="31d94-118">メッセージの圧縮は、TIBCO EMS クライアントで EMS に圧縮形式でメッセージを送信できるようにがで使用できない、 C# API。</span><span class="sxs-lookup"><span data-stu-id="31d94-118">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="31d94-119">アダプターとサーバー間のメッセージの暗号化では使用できない、 C# API。</span><span class="sxs-lookup"><span data-stu-id="31d94-119">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="31d94-120">C# OpenSSL ライブラリを使用して SSL 暗号化 API は許可されません。</span><span class="sxs-lookup"><span data-stu-id="31d94-120">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="31d94-121">C# API が EMS 用の管理 API をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="31d94-121">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="31d94-122">サイズが 50 MB を超えるメッセージは送信できませんまたは BizTalk TIBCO EMS アダプターを使用して受信します。</span><span class="sxs-lookup"><span data-stu-id="31d94-122">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="31d94-123">環境では、このサイズを超えた System.OutOfMemoryException 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="31d94-123">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d94-124">参照</span><span class="sxs-lookup"><span data-stu-id="31d94-124">See Also</span></span>  
 [<span data-ttu-id="31d94-125">計画および設計</span><span class="sxs-lookup"><span data-stu-id="31d94-125">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)