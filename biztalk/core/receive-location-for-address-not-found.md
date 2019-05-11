---
title: 受信場所のアドレスが見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17aa261f12d7783a15b998c5eed9743ee7af07dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398222"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="2a88c-102">アドレスの受信場所が見つかりません</span><span class="sxs-lookup"><span data-stu-id="2a88c-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="2a88c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2a88c-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2a88c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2a88c-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="2a88c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2a88c-105">Product Version</span></span> |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="2a88c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2a88c-106">Event ID</span></span>     |                                               <span data-ttu-id="2a88c-107">0</span><span class="sxs-lookup"><span data-stu-id="2a88c-107">0</span></span>                                               |
|  <span data-ttu-id="2a88c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2a88c-108">Event Source</span></span>   |                                               <span data-ttu-id="2a88c-109">0</span><span class="sxs-lookup"><span data-stu-id="2a88c-109">0</span></span>                                               |
|    <span data-ttu-id="2a88c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a88c-110">Component</span></span>    |                                               <span data-ttu-id="2a88c-111">0</span><span class="sxs-lookup"><span data-stu-id="2a88c-111">0</span></span>                                               |
|  <span data-ttu-id="2a88c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2a88c-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="2a88c-113">0</span><span class="sxs-lookup"><span data-stu-id="2a88c-113">0</span></span>                                               |
|  <span data-ttu-id="2a88c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2a88c-114">Message Text</span></span>   | <span data-ttu-id="2a88c-115">アドレスの受信場所"{0}"が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a88c-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="2a88c-116">(BizTalk 受信場所が無効になっています)。</span><span class="sxs-lookup"><span data-stu-id="2a88c-116">(The BizTalk receive location may be disabled.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2a88c-117">説明</span><span class="sxs-lookup"><span data-stu-id="2a88c-117">Explanation</span></span>  
 <span data-ttu-id="2a88c-118">このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応する受信場所。</span><span class="sxs-lookup"><span data-stu-id="2a88c-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a88c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2a88c-119">User Action</span></span>  
 <span data-ttu-id="2a88c-120">このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a88c-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="2a88c-121">作成の詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="2a88c-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="2a88c-122">分離 WCF 受信アダプターでの WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="2a88c-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="2a88c-123">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2a88c-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="2a88c-124">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2a88c-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="2a88c-125">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2a88c-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="2a88c-126">チュートリアル: Wcf-basichttp アダプターで WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="2a88c-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)