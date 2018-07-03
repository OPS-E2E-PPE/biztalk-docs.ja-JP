---
title: AS2 メッセージを検証するときにエラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac51c94b1a414a7cef5d7777eb4dcd08845e5d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996347"
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a><span data-ttu-id="9233a-102">AS2 メッセージの検証中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="9233a-102">An error occurred when validating an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="9233a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9233a-103">Details</span></span>  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9233a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9233a-104">Product Name</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| <span data-ttu-id="9233a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9233a-105">Product Version</span></span> |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    <span data-ttu-id="9233a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9233a-106">Event ID</span></span>     |                                                           -                                                           |
|  <span data-ttu-id="9233a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9233a-107">Event Source</span></span>   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9233a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9233a-108"> EDI</span></span>                 |
|    <span data-ttu-id="9233a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9233a-109">Component</span></span>    |                                                      <span data-ttu-id="9233a-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9233a-110">AS2 Engine</span></span>                                                       |
|  <span data-ttu-id="9233a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9233a-111">Symbolic Name</span></span>  |                                                           -                                                           |
|  <span data-ttu-id="9233a-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9233a-112">Message Text</span></span>   | <span data-ttu-id="9233a-113">AS2 メッセージの検証中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9233a-113">An error occurred when validating an AS2 message.</span></span> <span data-ttu-id="9233a-114">使用した証明書の有効期限が切れていないこと、および失効していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9233a-114">Make sure the certificates used have not timed out or been revoked.</span></span> |

## <a name="explanation"></a><span data-ttu-id="9233a-115">説明</span><span class="sxs-lookup"><span data-stu-id="9233a-115">Explanation</span></span>  
 <span data-ttu-id="9233a-116">このエラー/警告/情報イベントは、AS2 受信パイプラインまたは AS2 送信パイプラインで AS2 メッセージを検証できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9233a-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not validate the AS2 message.</span></span> <span data-ttu-id="9233a-117">これは、署名の確認プロセスで使用された証明書が有効でないか、適切な場所に格納されていないか、署名プロセスで使用された証明書と一致しない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9233a-117">This can occur if the certificate used in the signature verification process is not valid, is not stored in the appropriate location, or does not match the certificate used in the signing process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9233a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9233a-118">User Action</span></span>  
 <span data-ttu-id="9233a-119">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9233a-119">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="9233a-120">AS2 メッセージの署名ラッパーが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-120">Verify that the signature wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="9233a-121">有効でない場合は、メッセージがエンコーダーによって適切に署名されていない理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-121">If not, determine why the message was signed improperly by the encoder.</span></span>  

- <span data-ttu-id="9233a-122">署名プロセスで使用される秘密キーと、署名の確認プロセスで使用される公開キーが一致しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-122">Verify that the private key used in the signing process and the public key used in the signature verification process match.</span></span>  

- <span data-ttu-id="9233a-123">署名および署名の確認に使用される証明書の "キー使用法" プロパティが "データの暗号化" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-123">Verify that the Key Usage property of the certificate used for signing and signature verification is set to "data encipherment".</span></span>  

- <span data-ttu-id="9233a-124">中間証明機関のチェーンが切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-124">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="9233a-125">切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="9233a-125">If there is, delete the old certificate, and create and use a new certificate.</span></span>  

- <span data-ttu-id="9233a-126">証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-126">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  

- <span data-ttu-id="9233a-127">証明書失効リストを調べて、証明書が失効していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-127">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="9233a-128">(BizTalk Server が AS2 の全般プロパティで証明書失効リストのチェック プロパティをチェックして自動的に確認することが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。</span><span class="sxs-lookup"><span data-stu-id="9233a-128">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  

- <span data-ttu-id="9233a-129">署名の確認に使用される証明書が、ホスト インスタンス サービス アカウントごとに MIME/SMIME デコーダー パイプラインをホストする各 BizTalk サーバーの [ローカル コンピューター/その他のユーザー] ストアに格納されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9233a-129">Verify that the certificate used for signature verification is stored in the Local computer/Other People store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>
