---
title: HTTP アダプター サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1747a9bb28bc84dc0f6772435411d07557bf463e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383109"
---
# <a name="http-adapter-samples"></a><span data-ttu-id="1d952-102">HTTP アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="1d952-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="1d952-103">このセクションには、BizTalk HTTP アダプターを使用するときは、高度な機能を示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d952-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d952-104">このサンプルを実行する前に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d952-104">Before running this sample, you need to do the following steps:</span></span>  
> 
> 1. <span data-ttu-id="1d952-105">IIS を開き、ISAPI および CGI の制限を追加します。</span><span class="sxs-lookup"><span data-stu-id="1d952-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
> 
>    <span data-ttu-id="1d952-106">左側のパネルでコンピューター名をクリックし、右側のパネルし、追加、ISAPI または CGI パスに"ISAPI および CGI の制限 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d952-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
> 
>    <span data-ttu-id="1d952-107">64 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="1d952-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="1d952-108">32 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="1d952-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="1d952-109">許可された拡張パスを確認するかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d952-109">Check allowed extension path or execute.</span></span>  
>    2.  <span data-ttu-id="1d952-110">左側のパネルで HTTPRequestResponseSample をクリックし、中央のパネルで ハンドラー マッピング をクリックし、次の設定の"スクリプト マップの追加 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d952-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
> 
>    <span data-ttu-id="1d952-111">要求パス: btshttpreceive.dll</span><span class="sxs-lookup"><span data-stu-id="1d952-111">Request path:BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="1d952-112">実行可能ファイル:</span><span class="sxs-lookup"><span data-stu-id="1d952-112">Executable:</span></span>  
> 
>    <span data-ttu-id="1d952-113">64 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="1d952-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span></span>  
> 
>    <span data-ttu-id="1d952-114">32 ビット コンピューターを追加します。 C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\HttpReceive\\</span><span class="sxs-lookup"><span data-stu-id="1d952-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span></span>  
> 
>    <span data-ttu-id="1d952-115">要求の制限。</span><span class="sxs-lookup"><span data-stu-id="1d952-115">Request restrictions:</span></span>  
> 
>    <span data-ttu-id="1d952-116">動詞:POST</span><span class="sxs-lookup"><span data-stu-id="1d952-116">Verbs: POST</span></span>  
> 
>    <span data-ttu-id="1d952-117">アクセス:[スクリプト]</span><span class="sxs-lookup"><span data-stu-id="1d952-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d952-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d952-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1d952-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="1d952-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="1d952-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="1d952-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)