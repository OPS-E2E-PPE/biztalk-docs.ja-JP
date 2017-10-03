---
title: "AS2 パーティに署名証明書が構成されていません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61802b5e86319d0fe73f11c22249b72af1441b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="46108-102">AS2 パーティに署名証明書が構成されていません</span><span class="sxs-lookup"><span data-stu-id="46108-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="46108-103">詳細</span><span class="sxs-lookup"><span data-stu-id="46108-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46108-104">製品名</span><span class="sxs-lookup"><span data-stu-id="46108-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="46108-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="46108-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="46108-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="46108-106">Event ID</span></span>|-|  
|<span data-ttu-id="46108-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="46108-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="46108-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="46108-108"> EDI</span></span>|  
|<span data-ttu-id="46108-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="46108-109">Component</span></span>|<span data-ttu-id="46108-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="46108-110">AS2 Engine</span></span>|  
|<span data-ttu-id="46108-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="46108-111">Symbolic Name</span></span>|<span data-ttu-id="46108-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="46108-112">SigningCertNotConfiguredError</span></span>|  
|<span data-ttu-id="46108-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="46108-113">Message Text</span></span>|<span data-ttu-id="46108-114">AS2 パーティに署名証明書が構成されていません。</span><span class="sxs-lookup"><span data-stu-id="46108-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="46108-115">AS2-から: {0} AS2-を: {1}</span><span class="sxs-lookup"><span data-stu-id="46108-115">AS2-From: {0} AS2-To: {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46108-116">説明</span><span class="sxs-lookup"><span data-stu-id="46108-116">Explanation</span></span>  
 <span data-ttu-id="46108-117">このエラー/警告/情報イベントは、グループに署名証明書が構成されていなかったため、送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="46108-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46108-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="46108-118">User Action</span></span>  
 <span data-ttu-id="46108-119">このエラーを解決するには、次の操作を行って署名証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="46108-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="46108-120">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="46108-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="46108-121">[グループ] ノードに移動し、[証明書] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="46108-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="46108-122">証明書の共通名と拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="46108-122">Enter the common name and thumbprint of the certificate.</span></span>