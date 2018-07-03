---
title: SOAP アダプターを使用した証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0a709ab6b28796328677e7e8ae009e3273565a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012283"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a><span data-ttu-id="52373-102">SOAP アダプターを使用した証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="52373-102">How to Configure Certificates with a SOAP Adapter</span></span>
<span data-ttu-id="52373-103">SOAP 送信アダプタを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="52373-103">The SOAP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="52373-104">クライアント証明書を指定した場合、SOAP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="52373-104">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="52373-105">クライアント証明書を指定しないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、SOAP 送信アダプターはメッセージを送信に失敗し、標準の再試行ロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="52373-105">If you do not specify a client certificate and the destination server requires client certificates, the sender is not authenticated and the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="52373-106">SOAP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="52373-106">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="52373-107">SOAP アダプタは拇印によって証明書を特定します。</span><span class="sxs-lookup"><span data-stu-id="52373-107">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="52373-108">SOAP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="52373-108">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="52373-109">を暗号化または署名されたメッセージを送信する SOAP アダプタを使用する場合は、送信ポートのクライアント証明書の拇印の SOAP トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="52373-109">When using a SOAP adapter to send an encrypted or signed message, configure the Client Certificate Thumbprint SOAP transport property for the send port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="52373-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="52373-110">Prerequisites</span></span>  
 <span data-ttu-id="52373-111">このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="52373-111">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a><span data-ttu-id="52373-112">SOAP 接続経由でメッセージを送信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="52373-112">To configure BizTalk Server to send messages over a SOAP connection</span></span>  

1. <span data-ttu-id="52373-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい SOAP 送信ポートを作成または既存の SOAP 送信ポートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="52373-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new SOAP send port or open the properties for an existing SOAP send port.</span></span>  

2. <span data-ttu-id="52373-114">クリックして**構成**で、**トランスポート**のセクション、**送信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="52373-114">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="52373-115">**全般**] タブの [**認証の種類**を選択します**Anonymous**、**基本的な**、**ダイジェスト**、または**NTLM**します。</span><span class="sxs-lookup"><span data-stu-id="52373-115">On the **General** tab, in **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **NTLM**.</span></span>  

4. <span data-ttu-id="52373-116">場合、認証の種類は**基本的な**または**ダイジェスト**、選択するか**シングル サインオンを使用しないでください**後者を指定してください、ユーザー名とパスワード) またはを選択します。**シングル サインオンを使用して、** (この場合、関連アプリケーションを選択する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="52373-116">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  

5. <span data-ttu-id="52373-117">**SSL クライアント証明書の拇印**、適切な拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="52373-117">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

6. <span data-ttu-id="52373-118">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="52373-118">Click **OK**, and then click **OK** again.</span></span>
