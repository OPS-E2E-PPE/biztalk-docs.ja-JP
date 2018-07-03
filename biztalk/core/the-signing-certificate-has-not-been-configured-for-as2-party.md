---
title: AS2 パーティの署名証明書が構成されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d26323670f0229377b304e5f51671de8ef10021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967547"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="0b13f-102">AS2 パーティに署名証明書が構成されていません</span><span class="sxs-lookup"><span data-stu-id="0b13f-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="0b13f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0b13f-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0b13f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0b13f-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="0b13f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0b13f-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="0b13f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0b13f-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="0b13f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0b13f-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0b13f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0b13f-108"> EDI</span></span>   |
|    <span data-ttu-id="0b13f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b13f-109">Component</span></span>    |                                        <span data-ttu-id="0b13f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="0b13f-110">AS2 Engine</span></span>                                         |
|  <span data-ttu-id="0b13f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0b13f-111">Symbolic Name</span></span>  |                               <span data-ttu-id="0b13f-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="0b13f-112">SigningCertNotConfiguredError</span></span>                               |
|  <span data-ttu-id="0b13f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0b13f-113">Message Text</span></span>   | <span data-ttu-id="0b13f-114">AS2 パーティに署名証明書が構成されていません。</span><span class="sxs-lookup"><span data-stu-id="0b13f-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="0b13f-115">AS2-から: {0} AS2-に。 {1}</span><span class="sxs-lookup"><span data-stu-id="0b13f-115">AS2-From: {0} AS2-To: {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0b13f-116">説明</span><span class="sxs-lookup"><span data-stu-id="0b13f-116">Explanation</span></span>  
 <span data-ttu-id="0b13f-117">このエラー/警告/情報イベントは、グループに署名証明書が構成されていなかったため、送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0b13f-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b13f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0b13f-118">User Action</span></span>  
 <span data-ttu-id="0b13f-119">このエラーを解決するには、次の操作を行って署名証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b13f-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="0b13f-120">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b13f-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="0b13f-121">[グループ] ノードに移動し、[証明書] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b13f-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="0b13f-122">証明書の共通名と拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="0b13f-122">Enter the common name and thumbprint of the certificate.</span></span>