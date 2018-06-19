---
title: 分離受信場所のアドレスを登録できませんでした |Microsoft ドキュメント
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
ms.openlocfilehash: edd55360a1638128ed687cf83f2e05bf52ad9dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246026"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a><span data-ttu-id="b5060-102">アドレスの分離受信場所を登録できませんでした</span><span class="sxs-lookup"><span data-stu-id="b5060-102">Failed to register isolated receiver for address</span></span>
## <a name="details"></a><span data-ttu-id="b5060-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b5060-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5060-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b5060-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b5060-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b5060-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b5060-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b5060-106">Event ID</span></span>|<span data-ttu-id="b5060-107">0</span><span class="sxs-lookup"><span data-stu-id="b5060-107">0</span></span>|  
|<span data-ttu-id="b5060-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b5060-108">Event Source</span></span>|<span data-ttu-id="b5060-109">0</span><span class="sxs-lookup"><span data-stu-id="b5060-109">0</span></span>|  
|<span data-ttu-id="b5060-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b5060-110">Component</span></span>|<span data-ttu-id="b5060-111">0</span><span class="sxs-lookup"><span data-stu-id="b5060-111">0</span></span>|  
|<span data-ttu-id="b5060-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b5060-112">Symbolic Name</span></span>|<span data-ttu-id="b5060-113">0</span><span class="sxs-lookup"><span data-stu-id="b5060-113">0</span></span>|  
|<span data-ttu-id="b5060-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b5060-114">Message Text</span></span>|<span data-ttu-id="b5060-115">アドレス "{0}" の分離受信場所を登録できませんでした。受信場所が存在しないか、無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b5060-115">Failed to register isolated receiver for address "{0}"; receive location does not exist or is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5060-116">説明</span><span class="sxs-lookup"><span data-stu-id="b5060-116">Explanation</span></span>  
 <span data-ttu-id="b5060-117">このエラーは、公開された WCF 分離受信場所に対応する受信場所が見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b5060-117">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5060-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b5060-118">User Action</span></span>  
 <span data-ttu-id="b5060-119">このエラーを解決するのには、次の操作: BizTalk 管理コンソールで、BizTalk WCF サービス公開ウィザード生成が存在し、ある Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認してください開始しました。</span><span class="sxs-lookup"><span data-stu-id="b5060-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Services Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="b5060-120">受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5060-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b5060-121">発行の WCF サービスを分離 WCF 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="b5060-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="b5060-122">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b5060-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="b5060-123">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b5060-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="b5060-124">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b5060-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="b5060-125">チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行</span><span class="sxs-lookup"><span data-stu-id="b5060-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)