---
title: "HTTP アダプター サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eb20ba2a9dc91f9b8bd17442f8bd3e7986fcfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-samples"></a><span data-ttu-id="c45cb-102">HTTP アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="c45cb-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="c45cb-103">このセクションでは、BizTalk HTTP アダプターを使用するときの高度な機能を示すサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c45cb-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c45cb-104">このサンプルを実行する前に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c45cb-104">Before running this sample, you need to do the following steps:</span></span>  
>   
>  1.  <span data-ttu-id="c45cb-105">IIS を開き、ISAPI および CGI の制限を追加します。</span><span class="sxs-lookup"><span data-stu-id="c45cb-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
>   
>      <span data-ttu-id="c45cb-106">左側のパネルでコンピューター名をクリックし、右側のパネルで [ISAPI および CGI の制限] をクリックして、次の ISAPI または CGI パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c45cb-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
>   
>      <span data-ttu-id="c45cb-107">64 ビット コンピューター上の追加: C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン > \HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="c45cb-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="c45cb-108">32 ビット コンピューターを追加します C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン > \HttpReceive\BTSHTTPReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="c45cb-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version>\HttpReceive\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="c45cb-109">許可された拡張パスを確認するか、または実行します。</span><span class="sxs-lookup"><span data-stu-id="c45cb-109">Check allowed extension path or execute.</span></span>  
> 2.  <span data-ttu-id="c45cb-110">左側のパネルで [HTTPRequestResponseSample] をクリックし、中央のパネルで [ハンドラー マッピング] をクリックし、[スクリプト マップの追加] をクリックして、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="c45cb-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
>   
>      <span data-ttu-id="c45cb-111">要求パス: BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="c45cb-111">Request path:BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="c45cb-112">実行可能ファイル:</span><span class="sxs-lookup"><span data-stu-id="c45cb-112">Executable:</span></span>  
>   
>      <span data-ttu-id="c45cb-113">64 ビット コンピューター上の追加: C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン > \HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="c45cb-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version>\HttpReceive64\\</span></span>  
>   
>      <span data-ttu-id="c45cb-114">32 ビット コンピューターを追加します C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン > \HttpReceive\。</span><span class="sxs-lookup"><span data-stu-id="c45cb-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version>\HttpReceive\\</span></span>  
>   
>      <span data-ttu-id="c45cb-115">要求の制限:</span><span class="sxs-lookup"><span data-stu-id="c45cb-115">Request restrictions:</span></span>  
>   
>      <span data-ttu-id="c45cb-116">動詞: POST</span><span class="sxs-lookup"><span data-stu-id="c45cb-116">Verbs: POST</span></span>  
>   
>      <span data-ttu-id="c45cb-117">アクセス: スクリプト</span><span class="sxs-lookup"><span data-stu-id="c45cb-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c45cb-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c45cb-118">In This Section</span></span>  
  
-   [<span data-ttu-id="c45cb-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="c45cb-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="c45cb-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="c45cb-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)