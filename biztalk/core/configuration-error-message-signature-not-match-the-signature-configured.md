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
ms.openlocfilehash: 729fff283d8fa63ce9e933a0dc69a4a8f2200874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980459"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a><span data-ttu-id="ed126-103">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="ed126-103">Configuration error.</span></span> <span data-ttu-id="ed126-104">メッセージの署名は&#39;このパーティ用に構成された署名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="ed126-104">The message signature doesn&#39;t match the signature configured for this party</span></span>
## <a name="details"></a><span data-ttu-id="ed126-105">詳細</span><span class="sxs-lookup"><span data-stu-id="ed126-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ed126-106">製品名</span><span class="sxs-lookup"><span data-stu-id="ed126-106">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="ed126-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ed126-107">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="ed126-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ed126-108">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="ed126-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ed126-109">Event Source</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ed126-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="ed126-110"> EDI</span></span>                                                           |
|    <span data-ttu-id="ed126-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ed126-111">Component</span></span>    |                                                                                                 <span data-ttu-id="ed126-112">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="ed126-112">AS2 Engine</span></span>                                                                                                 |
|  <span data-ttu-id="ed126-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ed126-113">Symbolic Name</span></span>  |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="ed126-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ed126-114">Message Text</span></span>   | <span data-ttu-id="ed126-115">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="ed126-115">Configuration error.</span></span> <span data-ttu-id="ed126-116">メッセージの署名がこのパーティ用に構成された署名と一致しません。</span><span class="sxs-lookup"><span data-stu-id="ed126-116">The message signature doesn't match the signature configured for this party.</span></span> <span data-ttu-id="ed126-117">送信元パートナーに問い合わせて、使用された証明書を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ed126-117">Contact the sending partner and verify the certificate used.</span></span> <span data-ttu-id="ed126-118">AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="ed126-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ed126-119">説明</span><span class="sxs-lookup"><span data-stu-id="ed126-119">Explanation</span></span>  
 <span data-ttu-id="ed126-120">このエラー/警告/情報イベントは、MIME 処理の実行時に AS2 受信パイプラインで署名を検証できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ed126-120">This Error/Warning/Information event indicates that the AS2 receive pipeline could not verify the signature when performing MIME processing.</span></span> <span data-ttu-id="ed126-121">この原因として、送信者がメッセージの署名に使用したものとは異なる証明書を使用して、受信したメッセージを処理した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ed126-121">This could result from using a different certificate to process the received message than the sender used to sign the message.</span></span> <span data-ttu-id="ed126-122">BizTalk Server が間違ったパーティの設定を使用して、受信した AS2 メッセージの署名を検証した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ed126-122">This can occur if BizTalk Server uses the settings of the wrong party to verify the signature of the incoming AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed126-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ed126-123">User Action</span></span>  
 <span data-ttu-id="ed126-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed126-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ed126-125">受信 AS2 メッセージに対して、パーティ解決プロセスで正しいパーティが特定されるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed126-125">Ensure that the correct party is determined by the party resolution process for the incoming AS2 message.</span></span> <span data-ttu-id="ed126-126">そのためには、BizTalk Server が、受信メッセージの AS2-From ヘッダーと、[パーティのプロパティ] ダイアログ ボックスの [全般] ページの [エイリアス] 一覧にある EDIINT-AS2 From の値を照合しようとするときに、正しいパーティが解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed126-126">Do so by verifying that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From header in the incoming message and the value for EDIINT-AS2 From in the Aliases list in the General page of the Party Properties dialog box.</span></span> <span data-ttu-id="ed126-127">パーティが解決されない場合は、BizTalk Server が、受信メッセージに対して設定されている AS2-From コンテキスト プロパティと、パーティの名前との一致を見つけようとするときに、正しいパーティが解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed126-127">If that does not resolve the party, verify that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From context property that is set for the incoming message and the name of a party.</span></span>  
  
-   <span data-ttu-id="ed126-128">[パーティのプロパティ] ダイアログ ボックスの [証明書] ページに定義されている証明書と、"ローカル コンピューター\その他のユーザー" ストアに格納されている証明書が、メッセージの署名に使用される証明書に対応することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed126-128">Ensure that the certificate defined in the Certificate page of the Party Properties dialog box, and stored in the Local computer\Other People store, corresponds to the certificate used to sign the message.</span></span>