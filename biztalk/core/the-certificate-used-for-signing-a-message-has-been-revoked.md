---
title: メッセージの署名に使用する証明書が失効しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9a122f5b8d340ba1bed2dca5062edabf2d46e84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298911"
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a><span data-ttu-id="e5deb-102">メッセージの署名に使用する証明書が失効しています</span><span class="sxs-lookup"><span data-stu-id="e5deb-102">The certificate used for signing a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="e5deb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e5deb-103">Details</span></span>  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e5deb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e5deb-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="e5deb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e5deb-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    <span data-ttu-id="e5deb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e5deb-106">Event ID</span></span>     |                                            -                                             |
|  <span data-ttu-id="e5deb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e5deb-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e5deb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e5deb-108">EDI</span></span>  |
|    <span data-ttu-id="e5deb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e5deb-109">Component</span></span>    |                                        <span data-ttu-id="e5deb-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="e5deb-110">AS2 Engine</span></span>                                        |
|  <span data-ttu-id="e5deb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e5deb-111">Symbolic Name</span></span>  |                          <span data-ttu-id="e5deb-112">SigningCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="e5deb-112">SigningCertificateHasBeenRevokedError</span></span>                           |
|  <span data-ttu-id="e5deb-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e5deb-113">Message Text</span></span>   | <span data-ttu-id="e5deb-114">メッセージの署名に使用する証明書は失効しています。</span><span class="sxs-lookup"><span data-stu-id="e5deb-114">The certificate used for signing a message has been revoked.</span></span> <span data-ttu-id="e5deb-115">証明書の拇印: {0}</span><span class="sxs-lookup"><span data-stu-id="e5deb-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e5deb-116">説明</span><span class="sxs-lookup"><span data-stu-id="e5deb-116">Explanation</span></span>  
 <span data-ttu-id="e5deb-117">このエラー/警告/情報イベントは、署名証明書として識別された証明書が失効しているため、送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e5deb-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5deb-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e5deb-118">User Action</span></span>  
 <span data-ttu-id="e5deb-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5deb-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="e5deb-120">失効した証明書を置き換える新しい証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="e5deb-120">Create a new certificate to replaced the revoked certificate.</span></span> <span data-ttu-id="e5deb-121">[現在のユーザー] 証明書ストアに証明書を追加し、その証明書を [グループのプロパティ] ダイアログ ボックスの [証明書] ページで署名証明書として指定し、証明書の公開キーを AS2 メッセージの受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="e5deb-121">Add the certificate to the Current User certificate store, identify it as the signing certificate in the Certificate page of the Group Properties dialog box, and then send the public key of the certificate to the recipient of the AS2 message.</span></span>  
  
-   <span data-ttu-id="e5deb-122">失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e5deb-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>