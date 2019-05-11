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
ms.openlocfilehash: 8910b5877e05d72e52707c93b0fb0bf99ae78cd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398241"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="9557d-102">メタデータの受信場所が見つかりません</span><span class="sxs-lookup"><span data-stu-id="9557d-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="9557d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9557d-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9557d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9557d-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="9557d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9557d-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="9557d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9557d-106">Event ID</span></span>     |                                                                   <span data-ttu-id="9557d-107">0</span><span class="sxs-lookup"><span data-stu-id="9557d-107">0</span></span>                                                                   |
|  <span data-ttu-id="9557d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9557d-108">Event Source</span></span>   |                                                                   <span data-ttu-id="9557d-109">0</span><span class="sxs-lookup"><span data-stu-id="9557d-109">0</span></span>                                                                   |
|    <span data-ttu-id="9557d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9557d-110">Component</span></span>    |                                                                   <span data-ttu-id="9557d-111">0</span><span class="sxs-lookup"><span data-stu-id="9557d-111">0</span></span>                                                                   |
|  <span data-ttu-id="9557d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9557d-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="9557d-113">0</span><span class="sxs-lookup"><span data-stu-id="9557d-113">0</span></span>                                                                   |
|  <span data-ttu-id="9557d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9557d-114">Message Text</span></span>   | <span data-ttu-id="9557d-115">受信場所"{0}"のメタデータが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="9557d-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="9557d-116">(Web.config の受信場所マッピングを確認および受信場所が存在することを確認します。)</span><span class="sxs-lookup"><span data-stu-id="9557d-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9557d-117">説明</span><span class="sxs-lookup"><span data-stu-id="9557d-117">Explanation</span></span>  
 <span data-ttu-id="9557d-118">このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応するメタデータの受信場所。</span><span class="sxs-lookup"><span data-stu-id="9557d-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9557d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9557d-119">User Action</span></span>  
 <span data-ttu-id="9557d-120">このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9557d-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="9557d-121">詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="9557d-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9557d-122">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="9557d-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="9557d-123">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="9557d-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="9557d-124">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="9557d-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="9557d-125">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="9557d-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="9557d-126">チュートリアル: Wcf-netmsmq アダプターで WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="9557d-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)