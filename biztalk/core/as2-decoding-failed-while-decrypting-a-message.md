---
title: "AS2 のデコードがメッセージを暗号化解除中に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ef95ad35e1da933197bac11a9d80f98ddabd6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a><span data-ttu-id="9c59d-102">メッセージの復号中に、AS2 のデコードに失敗しました</span><span class="sxs-lookup"><span data-stu-id="9c59d-102">AS2 decoding failed while decrypting a message</span></span>
## <a name="details"></a><span data-ttu-id="9c59d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9c59d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c59d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9c59d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9c59d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9c59d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9c59d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9c59d-106">Event ID</span></span>|-|  
|<span data-ttu-id="9c59d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9c59d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9c59d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9c59d-108"> EDI</span></span>|  
|<span data-ttu-id="9c59d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9c59d-109">Component</span></span>|<span data-ttu-id="9c59d-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9c59d-110">AS2 Engine</span></span>|  
|<span data-ttu-id="9c59d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9c59d-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="9c59d-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9c59d-112">Message Text</span></span>|<span data-ttu-id="9c59d-113">メッセージの復号中に、AS2 のデコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9c59d-113">AS2 decoding failed while decrypting a message.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9c59d-114">説明</span><span class="sxs-lookup"><span data-stu-id="9c59d-114">Explanation</span></span>  
 <span data-ttu-id="9c59d-115">このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを解読できなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-115">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decrypt the AS2 message.</span></span> <span data-ttu-id="9c59d-116">この問題は、解読のプロセスで使用された証明書が、有効でないか、適切な場所に置かれていないか、暗号化のプロセスで使用された証明書と一致していない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9c59d-116">This can occur if the certificate used in the decryption process is not valid, is not stored in the appropriate location, or does not match the certificate used in the encryption process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c59d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9c59d-117">User Action</span></span>  
 <span data-ttu-id="9c59d-118">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-118">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="9c59d-119">AS2 メッセージの暗号化ラッパーが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-119">Verify that the encryption wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="9c59d-120">原因がそれ以外である場合は、メッセージがエンコーダーによって正しくエンコードされなかった理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-120">If not, determine why the message was encoded improperly by the encoder.</span></span>  
  
-   <span data-ttu-id="9c59d-121">暗号化のプロセスで使用された公開キーと、解読のプロセスで使用された秘密キーが一致しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-121">Verify that the public key used in the encryption process and the private key used in the decryption process match.</span></span>  
  
-   <span data-ttu-id="9c59d-122">暗号化と解読に使用された証明書の "キー使用法" プロパティが "データの暗号化" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-122">Verify that the Key Usage property of the certificate used for encryption and decryption is set to "data encipherment".</span></span>  
  
-   <span data-ttu-id="9c59d-123">中間証明機関のチェーンが切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-123">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="9c59d-124">切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-124">If there is, delete the old certificate, and create and use a new certificate.</span></span>  
  
-   <span data-ttu-id="9c59d-125">証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-125">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  
  
-   <span data-ttu-id="9c59d-126">証明書失効リストを調べて、証明書が失効していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-126">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="9c59d-127">(BizTalk Server が、証明書失効リストのチェック、AS2 の全般プロパティでプロパティを確認してこれを自動的に確認を持つことができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。</span><span class="sxs-lookup"><span data-stu-id="9c59d-127">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  
  
-   <span data-ttu-id="9c59d-128">解読に使用された証明書が、各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダー パイプラインをホストする各 BizTalk サーバーの "現在のユーザー\個人用" ストアに保存されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c59d-128">Verify that the certificate used for decryption is stored in the Current User\Personal store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>