---
title: 構成エラー。 メッセージの署名は&#39;このパーティ用に構成された署名が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b78dc27ff21787c6b57e65a2cadb7564e080c1a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391557"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a><span data-ttu-id="1b39f-103">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="1b39f-103">Configuration error.</span></span> <span data-ttu-id="1b39f-104">メッセージの署名は&#39;このパーティ用に構成された署名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="1b39f-104">The message signature doesn&#39;t match the signature configured for this party</span></span>
## <a name="details"></a><span data-ttu-id="1b39f-105">詳細</span><span class="sxs-lookup"><span data-stu-id="1b39f-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1b39f-106">製品名</span><span class="sxs-lookup"><span data-stu-id="1b39f-106">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="1b39f-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1b39f-107">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="1b39f-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1b39f-108">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="1b39f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1b39f-109">Event Source</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1b39f-110">EDI</span><span class="sxs-lookup"><span data-stu-id="1b39f-110">EDI</span></span>                                                           |
|    <span data-ttu-id="1b39f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1b39f-111">Component</span></span>    |                                                                                                 <span data-ttu-id="1b39f-112">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="1b39f-112">AS2 Engine</span></span>                                                                                                 |
|  <span data-ttu-id="1b39f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1b39f-113">Symbolic Name</span></span>  |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="1b39f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1b39f-114">Message Text</span></span>   | <span data-ttu-id="1b39f-115">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="1b39f-115">Configuration error.</span></span> <span data-ttu-id="1b39f-116">メッセージの署名は、このパーティ用に構成された署名と一致しません。</span><span class="sxs-lookup"><span data-stu-id="1b39f-116">The message signature doesn't match the signature configured for this party.</span></span> <span data-ttu-id="1b39f-117">送信元パートナーに連絡し、使用する証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="1b39f-117">Contact the sending partner and verify the certificate used.</span></span> <span data-ttu-id="1b39f-118">AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="1b39f-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1b39f-119">説明</span><span class="sxs-lookup"><span data-stu-id="1b39f-119">Explanation</span></span>  
 <span data-ttu-id="1b39f-120">このエラー/警告/情報イベントは、AS2 の受信を示す MIME 処理を実行するときに、パイプラインは、署名を確認できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1b39f-120">This Error/Warning/Information event indicates that the AS2 receive pipeline could not verify the signature when performing MIME processing.</span></span> <span data-ttu-id="1b39f-121">別の証明書を使用してメッセージに署名するために使用する送信者よりも、受信したメッセージを処理する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b39f-121">This could result from using a different certificate to process the received message than the sender used to sign the message.</span></span> <span data-ttu-id="1b39f-122">これは、BizTalk Server では、間違ったパーティの設定を使用して、受信 AS2 メッセージの署名を検証する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1b39f-122">This can occur if BizTalk Server uses the settings of the wrong party to verify the signature of the incoming AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b39f-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1b39f-123">User Action</span></span>  
 <span data-ttu-id="1b39f-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b39f-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="1b39f-125">受信 AS2 メッセージのパーティの解決プロセスで正しいパーティが決定されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b39f-125">Ensure that the correct party is determined by the party resolution process for the incoming AS2 message.</span></span> <span data-ttu-id="1b39f-126">BizTalk Server が AS2 の間の一致を検索しようとしたときに、正しいパーティが解決されるかを確認し、そのため、ヘッダー、着信メッセージとパーティのプロパティ ダイアログ ボックスの 全般 ページの エイリアス 一覧の ediint-as2 From の値。</span><span class="sxs-lookup"><span data-stu-id="1b39f-126">Do so by verifying that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From header in the incoming message and the value for EDIINT-AS2 From in the Aliases list in the General page of the Party Properties dialog box.</span></span> <span data-ttu-id="1b39f-127">パーティが解決しない場合は、BizTalk Server が AS2 の間の一致を検索しようとしたときに、正しいパーティが解決されることを確認の受信メッセージとパーティの名前に設定されているコンテキスト プロパティから。</span><span class="sxs-lookup"><span data-stu-id="1b39f-127">If that does not resolve the party, verify that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From context property that is set for the incoming message and the name of a party.</span></span>  
  
-   <span data-ttu-id="1b39f-128">パーティのプロパティ ダイアログ ボックスの 証明書 ページで定義され、Local computer \other People ストアに格納されている証明書は、メッセージの署名に使用する証明書に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b39f-128">Ensure that the certificate defined in the Certificate page of the Party Properties dialog box, and stored in the Local computer\Other People store, corresponds to the certificate used to sign the message.</span></span>