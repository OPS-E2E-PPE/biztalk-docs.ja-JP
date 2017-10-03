---
title: "メッセージの暗号化に使用する証明書が失効 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fbe34dcd2906d79a8d80ebdd00c3d9f293e6559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a><span data-ttu-id="656cd-102">メッセージの暗号化に使用する証明書は失効しています</span><span class="sxs-lookup"><span data-stu-id="656cd-102">The certificate used to encrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="656cd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="656cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="656cd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="656cd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="656cd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="656cd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="656cd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="656cd-106">Event ID</span></span>|-|  
|<span data-ttu-id="656cd-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="656cd-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="656cd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="656cd-108"> EDI</span></span>|  
|<span data-ttu-id="656cd-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="656cd-109">Component</span></span>|<span data-ttu-id="656cd-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="656cd-110">AS2 Engine</span></span>|  
|<span data-ttu-id="656cd-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="656cd-111">Symbolic Name</span></span>|<span data-ttu-id="656cd-112">EncryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="656cd-112">EncryptionCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="656cd-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="656cd-113">Message Text</span></span>|<span data-ttu-id="656cd-114">メッセージの暗号化に使用する証明書は失効しています。</span><span class="sxs-lookup"><span data-stu-id="656cd-114">The certificate used to encrypt a message has been revoked.</span></span> <span data-ttu-id="656cd-115">証明書の拇印: {0}</span><span class="sxs-lookup"><span data-stu-id="656cd-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="656cd-116">説明</span><span class="sxs-lookup"><span data-stu-id="656cd-116">Explanation</span></span>  
 <span data-ttu-id="656cd-117">このエラー/警告/情報イベントは、暗号化証明書として識別された証明書が失効しているため、送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="656cd-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the encryption certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="656cd-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="656cd-118">User Action</span></span>  
 <span data-ttu-id="656cd-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="656cd-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="656cd-120">メッセージの受信者に対して、新しい証明書を作成し、公開キーを送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="656cd-120">Have the receiver of the message create a new certificate and send the public key to you.</span></span> <span data-ttu-id="656cd-121">"ローカル コンピューター\その他のユーザー" 証明書ストアに証明書を追加し、[送信ポートのプロパティ] ダイアログ ボックスの [証明書] ページで、暗号化証明書としてその証明書を識別します。</span><span class="sxs-lookup"><span data-stu-id="656cd-121">Add the certificate to the Local computer\Other People certificate store, and then identify the certificate as the encryption certificate in the Certificate page of the Send Port Properties dialog box.</span></span>  
  
-   <span data-ttu-id="656cd-122">失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="656cd-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>