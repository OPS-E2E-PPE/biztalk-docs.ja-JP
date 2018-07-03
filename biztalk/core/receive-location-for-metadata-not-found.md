---
title: 見つかりませんメタデータの受信場所 |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ae137cc48d5df142c2917b0d40fd2bc95e36dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011595"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="ce9b2-102">メタデータの受信場所が見つかりません</span><span class="sxs-lookup"><span data-stu-id="ce9b2-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="ce9b2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ce9b2-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce9b2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ce9b2-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="ce9b2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ce9b2-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="ce9b2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ce9b2-106">Event ID</span></span>     |                                                                   <span data-ttu-id="ce9b2-107">0</span><span class="sxs-lookup"><span data-stu-id="ce9b2-107">0</span></span>                                                                   |
|  <span data-ttu-id="ce9b2-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ce9b2-108">Event Source</span></span>   |                                                                   <span data-ttu-id="ce9b2-109">0</span><span class="sxs-lookup"><span data-stu-id="ce9b2-109">0</span></span>                                                                   |
|    <span data-ttu-id="ce9b2-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ce9b2-110">Component</span></span>    |                                                                   <span data-ttu-id="ce9b2-111">0</span><span class="sxs-lookup"><span data-stu-id="ce9b2-111">0</span></span>                                                                   |
|  <span data-ttu-id="ce9b2-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ce9b2-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="ce9b2-113">0</span><span class="sxs-lookup"><span data-stu-id="ce9b2-113">0</span></span>                                                                   |
|  <span data-ttu-id="ce9b2-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ce9b2-114">Message Text</span></span>   | <span data-ttu-id="ce9b2-115">受信場所"{0}"のメタデータが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="ce9b2-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="ce9b2-116">(Web.config の受信場所マッピングを確認して、この受信場所が存在するか確認してください)。</span><span class="sxs-lookup"><span data-stu-id="ce9b2-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ce9b2-117">説明</span><span class="sxs-lookup"><span data-stu-id="ce9b2-117">Explanation</span></span>  
 <span data-ttu-id="ce9b2-118">このエラーは、公開された WCF 分離受信場所に、メタデータの対応する受信場所が見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ce9b2-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce9b2-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ce9b2-119">User Action</span></span>  
 <span data-ttu-id="ce9b2-120">このエラーを解決するのには、次の操作: BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce9b2-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="ce9b2-121">受信場所の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce9b2-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ce9b2-122">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="ce9b2-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="ce9b2-123">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ce9b2-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="ce9b2-124">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ce9b2-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="ce9b2-125">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ce9b2-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="ce9b2-126">チュートリアル: WCF-NetMsmq アダプターを使用した WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="ce9b2-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)