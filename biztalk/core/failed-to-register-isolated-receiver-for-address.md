---
title: アドレスの分離受信場所の登録に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7db73ecd84218f19dbc576ae3e94dec6cef4218d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388134"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a><span data-ttu-id="09e9d-102">アドレスの分離受信場所を登録できませんでした</span><span class="sxs-lookup"><span data-stu-id="09e9d-102">Failed to register isolated receiver for address</span></span>
## <a name="details"></a><span data-ttu-id="09e9d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="09e9d-103">Details</span></span>  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="09e9d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="09e9d-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="09e9d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="09e9d-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="09e9d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="09e9d-106">Event ID</span></span>     |                                                    <span data-ttu-id="09e9d-107">0</span><span class="sxs-lookup"><span data-stu-id="09e9d-107">0</span></span>                                                    |
|  <span data-ttu-id="09e9d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="09e9d-108">Event Source</span></span>   |                                                    <span data-ttu-id="09e9d-109">0</span><span class="sxs-lookup"><span data-stu-id="09e9d-109">0</span></span>                                                    |
|    <span data-ttu-id="09e9d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="09e9d-110">Component</span></span>    |                                                    <span data-ttu-id="09e9d-111">0</span><span class="sxs-lookup"><span data-stu-id="09e9d-111">0</span></span>                                                    |
|  <span data-ttu-id="09e9d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="09e9d-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="09e9d-113">0</span><span class="sxs-lookup"><span data-stu-id="09e9d-113">0</span></span>                                                    |
|  <span data-ttu-id="09e9d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="09e9d-114">Message Text</span></span>   | <span data-ttu-id="09e9d-115">アドレスの分離受信場所を登録できませんでした"{0}"; 受信場所が存在しないか無効にします。</span><span class="sxs-lookup"><span data-stu-id="09e9d-115">Failed to register isolated receiver for address "{0}"; receive location does not exist or is disabled.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="09e9d-116">説明</span><span class="sxs-lookup"><span data-stu-id="09e9d-116">Explanation</span></span>  
 <span data-ttu-id="09e9d-117">このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応する受信場所。</span><span class="sxs-lookup"><span data-stu-id="09e9d-117">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09e9d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="09e9d-118">User Action</span></span>  
 <span data-ttu-id="09e9d-119">このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで、BizTalk WCF サービス公開ウィザード生成が存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09e9d-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Services Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="09e9d-120">作成の詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="09e9d-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="09e9d-121">分離 WCF 受信アダプターでの WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="09e9d-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="09e9d-122">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="09e9d-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="09e9d-123">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="09e9d-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="09e9d-124">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="09e9d-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="09e9d-125">チュートリアル: Wcf-basichttp アダプターで WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="09e9d-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)