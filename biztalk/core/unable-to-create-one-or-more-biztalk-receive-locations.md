---
title: "BizTalk 受信場所を 1 つまたは複数を作成できません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b564f87b-34ba-400e-9a71-bd66081fc1b8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b87f8e4874f2f59f26a58a8c4f40f93e5073207c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-one-or-more-biztalk-receive-locations"></a><span data-ttu-id="c4d71-102">BizTalk 受信場所を 1 つ以上作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="c4d71-102">Unable to create one or more BizTalk receive locations</span></span>
## <a name="details"></a><span data-ttu-id="c4d71-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c4d71-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4d71-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c4d71-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c4d71-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c4d71-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="c4d71-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c4d71-106">Event ID</span></span>|<span data-ttu-id="c4d71-107">0</span><span class="sxs-lookup"><span data-stu-id="c4d71-107">0</span></span>|  
|<span data-ttu-id="c4d71-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c4d71-108">Event Source</span></span>|<span data-ttu-id="c4d71-109">0</span><span class="sxs-lookup"><span data-stu-id="c4d71-109">0</span></span>|  
|<span data-ttu-id="c4d71-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c4d71-110">Component</span></span>|<span data-ttu-id="c4d71-111">0</span><span class="sxs-lookup"><span data-stu-id="c4d71-111">0</span></span>|  
|<span data-ttu-id="c4d71-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c4d71-112">Symbolic Name</span></span>|<span data-ttu-id="c4d71-113">0</span><span class="sxs-lookup"><span data-stu-id="c4d71-113">0</span></span>|  
|<span data-ttu-id="c4d71-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c4d71-114">Message Text</span></span>|<span data-ttu-id="c4d71-115">BizTalk の受信場所を 1 つ以上作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c4d71-115">Unable to create one or more BizTalk receive locations.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c4d71-116">説明</span><span class="sxs-lookup"><span data-stu-id="c4d71-116">Explanation</span></span>  
 <span data-ttu-id="c4d71-117">このエラーは、BizTalk WCF サービス公開ウィザードで、分離 WCF アダプターをホストする受信場所の作成に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c4d71-117">This error indicates that the BizTalk WCF Publishing Wizard failed to create receive locations hosting an isolated WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c4d71-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c4d71-118">User Action</span></span>  
 <span data-ttu-id="c4d71-119">BizTalk インスタンスが起動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c4d71-119">Make sure that BizTalk instance is started.</span></span>  
  
 <span data-ttu-id="c4d71-120">受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d71-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation:</span></span>  
  
-   [<span data-ttu-id="c4d71-121">発行の WCF サービスを分離 WCF 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="c4d71-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="c4d71-122">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c4d71-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="c4d71-123">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c4d71-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="c4d71-124">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c4d71-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="c4d71-125">チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行</span><span class="sxs-lookup"><span data-stu-id="c4d71-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)