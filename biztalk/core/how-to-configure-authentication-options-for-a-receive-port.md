---
title: "認証を構成する方法のオプションは、受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012ec38ef3d9acf53c7293c668b17cd85c6c738d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="32834-102">受信ポートの認証オプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="32834-102">How to Configure Authentication Options for a Receive Port</span></span>
<span data-ttu-id="32834-103">このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートのメッセージ認証オプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32834-103">This topic describes how to use the BizTalk Server Administration console to configure message authentication options for a receive port.</span></span> <span data-ttu-id="32834-104">メッセージ認証オプションは、パーティの解決の認証が構成されると適用されます。</span><span class="sxs-lookup"><span data-stu-id="32834-104">These options take effect when party resolution authentication is configured.</span></span> <span data-ttu-id="32834-105">使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32834-105">The options are:</span></span>  
  
-   <span data-ttu-id="32834-106">**認証は行われません。**</span><span class="sxs-lookup"><span data-stu-id="32834-106">**No authentication.**</span></span> <span data-ttu-id="32834-107">このオプションを選択すると、受信ポートはメッセージの資格情報を確認せずにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="32834-107">If this option is selected, the receive port will pass the message through without checking for message credentials.</span></span>  
  
-   <span data-ttu-id="32834-108">**認証が失敗した場合は、メッセージを削除します。**</span><span class="sxs-lookup"><span data-stu-id="32834-108">**Drop messages if authentication fails.**</span></span> <span data-ttu-id="32834-109">このオプションを選択すると、受信ポートはパーティの解決を使用してメッセージの資格情報をチェックし、認証に失敗した場合はメッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="32834-109">If this option is selected, the receive port will check message credentials using Party resolution and discard the message if authentication fails.</span></span>  
  
-   <span data-ttu-id="32834-110">**認証に失敗した場合は、メッセージを保持します。**</span><span class="sxs-lookup"><span data-stu-id="32834-110">**Keep messages if authentication fails.**</span></span> <span data-ttu-id="32834-111">: このオプションを選択すると、受信ポートはパーティの解決を使用してメッセージの資格情報をチェックし、認証に失敗した場合はメッセージを保留キューに保持します。</span><span class="sxs-lookup"><span data-stu-id="32834-111">If this option is selected, the receive port will check message credentials using Party resolution and keep the message in the suspended queue if authentication fails.</span></span>  
  
 <span data-ttu-id="32834-112">作成し、パーティを構成する手順については、次を参照してください。[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)です。</span><span class="sxs-lookup"><span data-stu-id="32834-112">For instructions on creating and configuring a party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span> <span data-ttu-id="32834-113">パーティの解決の認証の詳細については、次を参照してください。[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)と[受信メッセージの認証](../core/inbound-message-authentication.md)です。</span><span class="sxs-lookup"><span data-stu-id="32834-113">For more information about party resolution authentication, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) and [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32834-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="32834-114">Prerequisites</span></span>  
 <span data-ttu-id="32834-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32834-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="32834-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="32834-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="32834-117">受信ポートの認証オプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="32834-117">To configure authentication options for a receive port</span></span>  
  
1.  <span data-ttu-id="32834-118">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="32834-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="32834-119">コンソール ツリーで、BizTalk グループを展開し、受信ポートの認証を構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="32834-119">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure authentication for a receive port.</span></span>  
  
3.  <span data-ttu-id="32834-120">をクリックして**受信ポート**受信ポートを右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="32834-120">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="32834-121">**認証**セクションのオプションを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="32834-121">In the **Authentication** section, select the option you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32834-122">参照</span><span class="sxs-lookup"><span data-stu-id="32834-122">See Also</span></span>  
 [<span data-ttu-id="32834-123">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="32834-123">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)