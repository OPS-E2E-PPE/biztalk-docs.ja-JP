---
title: AS2 のデコード、メッセージの解読中に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78dea4d186de1b4cfe34998abc3f627eae0e8977
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528556"
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a><span data-ttu-id="9acf0-102">AS2 のデコード、メッセージの解読中に失敗しました</span><span class="sxs-lookup"><span data-stu-id="9acf0-102">AS2 decoding failed while decrypting a message</span></span>
## <a name="details"></a><span data-ttu-id="9acf0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9acf0-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9acf0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9acf0-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9acf0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9acf0-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9acf0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9acf0-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9acf0-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9acf0-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9acf0-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9acf0-108">EDI</span></span> |
|    <span data-ttu-id="9acf0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9acf0-109">Component</span></span>    |                                       <span data-ttu-id="9acf0-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9acf0-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9acf0-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9acf0-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="9acf0-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9acf0-112">Message Text</span></span>   |                    <span data-ttu-id="9acf0-113">AS2 のデコードは、メッセージの解読中に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9acf0-113">AS2 decoding failed while decrypting a message.</span></span>                     |

## <a name="explanation"></a><span data-ttu-id="9acf0-114">説明</span><span class="sxs-lookup"><span data-stu-id="9acf0-114">Explanation</span></span>  
 <span data-ttu-id="9acf0-115">このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを解読できなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-115">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decrypt the AS2 message.</span></span> <span data-ttu-id="9acf0-116">この問題は、解読のプロセスで使用された証明書が、有効でないか、適切な場所に置かれていないか、暗号化のプロセスで使用された証明書と一致していない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9acf0-116">This can occur if the certificate used in the decryption process is not valid, is not stored in the appropriate location, or does not match the certificate used in the encryption process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9acf0-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9acf0-117">User Action</span></span>  
 <span data-ttu-id="9acf0-118">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-118">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="9acf0-119">AS2 メッセージの暗号化ラッパーが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-119">Verify that the encryption wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="9acf0-120">原因がそれ以外である場合は、メッセージがエンコーダーによって正しくエンコードされなかった理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-120">If not, determine why the message was encoded improperly by the encoder.</span></span>  

- <span data-ttu-id="9acf0-121">暗号化のプロセスで使用された公開キーと、解読のプロセスで使用された秘密キーが一致しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-121">Verify that the public key used in the encryption process and the private key used in the decryption process match.</span></span>  

- <span data-ttu-id="9acf0-122">暗号化と解読に使用された証明書の "キー使用法" プロパティが "データの暗号化" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-122">Verify that the Key Usage property of the certificate used for encryption and decryption is set to "data encipherment".</span></span>  

- <span data-ttu-id="9acf0-123">中間証明機関のチェーンが切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-123">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="9acf0-124">切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-124">If there is, delete the old certificate, and create and use a new certificate.</span></span>  

- <span data-ttu-id="9acf0-125">証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-125">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  

- <span data-ttu-id="9acf0-126">証明書失効リストを調べて、証明書が失効していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-126">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="9acf0-127">(BizTalk Server が AS2 の全般プロパティで証明書失効リストのチェック プロパティをチェックして自動的に確認することが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。</span><span class="sxs-lookup"><span data-stu-id="9acf0-127">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  

- <span data-ttu-id="9acf0-128">解読に使用された証明書が、各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダー パイプラインをホストする各 BizTalk サーバーの "現在のユーザー\個人用" ストアに保存されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9acf0-128">Verify that the certificate used for decryption is stored in the Current User\Personal store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>
