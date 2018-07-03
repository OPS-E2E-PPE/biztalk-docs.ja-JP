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
ms.openlocfilehash: 55b3744f6590ee706bcc3df4124f964306634ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994947"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="5ee38-102">アドレスの受信場所が見つかりません</span><span class="sxs-lookup"><span data-stu-id="5ee38-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="5ee38-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5ee38-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5ee38-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5ee38-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="5ee38-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5ee38-105">Product Version</span></span> |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="5ee38-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5ee38-106">Event ID</span></span>     |                                               <span data-ttu-id="5ee38-107">0</span><span class="sxs-lookup"><span data-stu-id="5ee38-107">0</span></span>                                               |
|  <span data-ttu-id="5ee38-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5ee38-108">Event Source</span></span>   |                                               <span data-ttu-id="5ee38-109">0</span><span class="sxs-lookup"><span data-stu-id="5ee38-109">0</span></span>                                               |
|    <span data-ttu-id="5ee38-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5ee38-110">Component</span></span>    |                                               <span data-ttu-id="5ee38-111">0</span><span class="sxs-lookup"><span data-stu-id="5ee38-111">0</span></span>                                               |
|  <span data-ttu-id="5ee38-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5ee38-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="5ee38-113">0</span><span class="sxs-lookup"><span data-stu-id="5ee38-113">0</span></span>                                               |
|  <span data-ttu-id="5ee38-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5ee38-114">Message Text</span></span>   | <span data-ttu-id="5ee38-115">アドレスの受信場所"{0}"が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5ee38-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="5ee38-116">(BizTalk 受信場所が無効になっている可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="5ee38-116">(The BizTalk receive location may be disabled.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5ee38-117">説明</span><span class="sxs-lookup"><span data-stu-id="5ee38-117">Explanation</span></span>  
 <span data-ttu-id="5ee38-118">このエラーは、公開された WCF 分離受信場所に対応する受信場所が見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5ee38-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5ee38-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5ee38-119">User Action</span></span>  
 <span data-ttu-id="5ee38-120">このエラーを解決するのには、次の操作: BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ee38-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="5ee38-121">受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee38-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="5ee38-122">分離 WCF 受信アダプターでの WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="5ee38-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="5ee38-123">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5ee38-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="5ee38-124">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5ee38-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="5ee38-125">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5ee38-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="5ee38-126">チュートリアル: WCF-BasicHttp アダプターを使用した WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="5ee38-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)