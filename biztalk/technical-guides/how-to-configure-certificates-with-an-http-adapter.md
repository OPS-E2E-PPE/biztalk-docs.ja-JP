---
title: HTTP アダプターでの証明書を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f74b0a88983ede90899dac908a5407f8406ec1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297842"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a><span data-ttu-id="9ce5d-102">HTTP アダプターでの証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="9ce5d-102">How to Configure Certificates with an HTTP Adapter</span></span>
<span data-ttu-id="9ce5d-103">HTTP 送信アダプタを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-103">The HTTP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="9ce5d-104">クライアント証明書を指定した場合、HTTP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-104">If a client certificate is specified, the HTTP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="9ce5d-105">クライアント証明書が指定されていない場合、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、HTTP 送信アダプターがメッセージの送信に失敗して、標準の再試行ロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the HTTP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="9ce5d-106">HTTP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-106">The HTTP send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="9ce5d-107">証明書は拇印によって指定します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="9ce5d-108">HTTP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-108">If the HTTP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
 <span data-ttu-id="9ce5d-109">を暗号化または署名されたメッセージを送信する HTTP アダプターを使用する場合は、SSL 証明書の拇印の送信ポートの HTTP トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-109">When using an HTTP adapter to send an encrypted or signed message, configure the SSL certificate thumbprint HTTP transport property for the send port.</span></span> <span data-ttu-id="9ce5d-110">このプロパティでは、メッセージの認証に使用する証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ce5d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="9ce5d-111">Prerequisites</span></span>  
 <span data-ttu-id="9ce5d-112">このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-112">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a><span data-ttu-id="9ce5d-113">HTTP 接続経由でメッセージを送信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="9ce5d-113">To configure BizTalk Server to send messages over an HTTP connection</span></span>  
  
1.  <span data-ttu-id="9ce5d-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい HTTP 送信ポートを作成するか既存の HTTP 送信ポートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new HTTP send port or open the properties for an existing HTTP send port.</span></span>  
  
2.  <span data-ttu-id="9ce5d-115">をクリックして**構成**のトランスポート セクションで、**送信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-115">Click **Configure** in the Transport section of the **Send Port Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="9ce5d-116">をクリックして**認証**で、 **HTTP トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-116">Click **Authentication** in the **HTTP Transport Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="9ce5d-117">**認証の種類****匿名**、**基本**、**ダイジェスト**、または**Kerberos**です。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-117">In **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **Kerberos**.</span></span>  
  
5.  <span data-ttu-id="9ce5d-118">認証の種類は場合**基本的な**または**ダイジェスト**を選択するか**シングル サインオンを使用しないでください**後者を指定してください、ユーザー名とパスワード) またはを選択**シングル サインオンを使用して**(この場合、関連アプリケーションを選択する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-118">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  
  
6.  <span data-ttu-id="9ce5d-119">**SSL クライアント証明書の拇印**、適切な拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-119">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  
  
7.  <span data-ttu-id="9ce5d-120">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="9ce5d-120">Click **OK**, and then click **OK** again.</span></span>