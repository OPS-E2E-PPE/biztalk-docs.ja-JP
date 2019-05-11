---
title: MSMQ アダプターを使用した証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd2e59f6e238d4af1e926ba7d85612520c402f9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253575"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a><span data-ttu-id="02e3a-102">MSMQ アダプターを使用した証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="02e3a-102">How to Configure Certificates with an MSMQ Adapter</span></span>
<span data-ttu-id="02e3a-103">MSMQ 送信アダプターを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="02e3a-103">The MSMQ send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="02e3a-104">クライアント証明書が指定されている場合、MSMQ 送信アダプターを必要とするか、クライアント証明書をそのまま使用するサーバーに接続するときに、証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-104">If a client certificate is specified, the MSMQ send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="02e3a-105">クライアント証明書が指定されていないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、MSMQ 送信アダプターはメッセージを送信に失敗し、標準の再試行ロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="02e3a-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the MSMQ send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="02e3a-106">MSMQ 送信アダプター クライアント証明書を使用するアカウントの個人用ストア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="02e3a-106">The MSMQ send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="02e3a-107">証明書は拇印によって指定します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="02e3a-108">MSMQ 送信アダプターは、何らかの理由で証明書の読み込みに失敗した場合、送信中だったメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="02e3a-108">If the MSMQ send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="02e3a-109">を暗号化または署名されたメッセージを送信する、MSMQ アダプターを使用する場合は、送信ポートに証明書の拇印の MSMQ トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-109">When using an MSMQ adapter to send an encrypted or signed message, configure the Certificate Thumbprint MSMQ transport property for the send port.</span></span> <span data-ttu-id="02e3a-110">このプロパティは、メッセージの認証に使用する証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span> <span data-ttu-id="02e3a-111">認証を使用するプロパティと組み合わせてこのプロパティを使用して、メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-111">Use this property in combination with the Use Authentication property to verify the message.</span></span> <span data-ttu-id="02e3a-112">キューにアクセスするのにには、ユーザー名とパスワードのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-112">Use the User Name and Password properties to gain access to queues.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="02e3a-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="02e3a-113">Prerequisites</span></span>  
 <span data-ttu-id="02e3a-114">このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="02e3a-114">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a><span data-ttu-id="02e3a-115">MSMQ 接続経由でメッセージを送信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="02e3a-115">To configure BizTalk Server to send messages over an MSMQ connection</span></span>  

1. <span data-ttu-id="02e3a-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい MSMQ 送信ポートを作成または既存の MSMQ 送信ポートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="02e3a-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new MSMQ send port or open the properties for an existing MSMQ send port.</span></span>  

2. <span data-ttu-id="02e3a-117">クリックして**構成**で、**トランスポート**のセクション、**送信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="02e3a-117">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="02e3a-118">**MSMQ トランスポートのプロパティ** ダイアログ ボックスの**認証**を選択します**True**します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-118">In the **MSMQ Transport Properties** dialog box, for **Authentication**, select **True**.</span></span>  

4. <span data-ttu-id="02e3a-119">**証明書の拇印**、適切な拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="02e3a-119">For **Certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

5. <span data-ttu-id="02e3a-120">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="02e3a-120">Click **OK**, and then click **OK** again.</span></span>
