---
title: メッセージの解読に使用する証明書が失効しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8302b4893b6014a260ce5f26e96138f7093bbf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298853"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a><span data-ttu-id="9e4e5-102">メッセージの解読に使用する証明書が失効しています</span><span class="sxs-lookup"><span data-stu-id="9e4e5-102">The certificate used to decrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="9e4e5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9e4e5-103">Details</span></span>  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9e4e5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9e4e5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="9e4e5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9e4e5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    <span data-ttu-id="9e4e5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9e4e5-106">Event ID</span></span>     |                                            -                                            |
|  <span data-ttu-id="9e4e5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9e4e5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9e4e5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9e4e5-108">EDI</span></span>  |
|    <span data-ttu-id="9e4e5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9e4e5-109">Component</span></span>    |                                       <span data-ttu-id="9e4e5-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9e4e5-110">AS2 Engine</span></span>                                        |
|  <span data-ttu-id="9e4e5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9e4e5-111">Symbolic Name</span></span>  |                        <span data-ttu-id="9e4e5-112">DecryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="9e4e5-112">DecryptionCertificateHasBeenRevokedError</span></span>                         |
|  <span data-ttu-id="9e4e5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9e4e5-113">Message Text</span></span>   | <span data-ttu-id="9e4e5-114">メッセージの解読に使用する証明書が失効しています。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-114">The certificate used to decrypt a message has been revoked.</span></span> <span data-ttu-id="9e4e5-115">証明書の拇印: {0}</span><span class="sxs-lookup"><span data-stu-id="9e4e5-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9e4e5-116">説明</span><span class="sxs-lookup"><span data-stu-id="9e4e5-116">Explanation</span></span>  
 <span data-ttu-id="9e4e5-117">このエラー/警告/情報イベントは、メッセージの解読に使用される証明書が失効しているためにで、受信メッセージが受信パイプラインでした処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message because the certificate to be used to decrypt the message has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e4e5-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9e4e5-118">User Action</span></span>  
 <span data-ttu-id="9e4e5-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="9e4e5-120">失効した証明書を置換する新しい証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-120">Create a new certificate to replace the revoked certificate.</span></span> <span data-ttu-id="9e4e5-121">現在のユーザー/個人用証明書ストアに証明書を追加し、AS2 メッセージを送信する証明書の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-121">Add the certificate to the Current User/Personal certificate store, and then send the public key of the certificate to the sending of the AS2 message.</span></span>  
  
-   <span data-ttu-id="9e4e5-122">失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9e4e5-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>