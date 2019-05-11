---
title: ルーティングを有効にする方法が失敗したメッセージの受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7410e7828acdf4968004e9a02bda4e4a26973260
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385120"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="58485-102">受信ポートが処理に失敗したメッセージのルーティングを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="58485-102">How to Enable Routing for Failed Messages for a Receive Port</span></span>
<span data-ttu-id="58485-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートが処理するメッセージのルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58485-103">This topic describes how to use the BizTalk Server Administration console to enable routing for the messages processed by a receive port.</span></span> <span data-ttu-id="58485-104">このオプションを有効にすると、処理に失敗したメッセージが、他の送信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="58485-104">When you enable this option, BizTalk Server will attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="58485-105">このオプションを無効にした場合 (既定)、失敗したメッセージは中断され、否定受信確認応答 (NACK) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="58485-105">When this option is not enabled (the default), BizTalk Server suspends failed messages and generates a negative acknowledgment (NACK).</span></span> <span data-ttu-id="58485-106">失敗したメッセージの管理に関する背景情報は、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。</span><span class="sxs-lookup"><span data-stu-id="58485-106">For background information about managing failed messages, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58485-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="58485-107">Prerequisites</span></span>  
 <span data-ttu-id="58485-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58485-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="58485-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="58485-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="58485-110">受信ポートが処理に失敗したメッセージのルーティングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="58485-110">To enable routing for failed messages for a receive port</span></span>  
  
1. <span data-ttu-id="58485-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="58485-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="58485-112">コンソール ツリーで、BizTalk グループを展開し、失敗したメッセージのルーティングを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="58485-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure failed message routing for a receive port.</span></span>  
  
3. <span data-ttu-id="58485-113">クリックして**受信ポート**受信ポートを右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="58485-113">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="58485-114">選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**OK**。</span><span class="sxs-lookup"><span data-stu-id="58485-114">Select the **Enable routing for failed messages** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58485-115">参照</span><span class="sxs-lookup"><span data-stu-id="58485-115">See Also</span></span>  
 [<span data-ttu-id="58485-116">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="58485-116">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)