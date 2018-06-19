---
title: 送信マップを構成する方法、受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248514"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="58969-102">受信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="58969-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="58969-103">このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートの送信マップを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58969-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="58969-104">要求 - 応答の受信ポートと共に送信マップを使用すると、送信メッセージのスキーマを別のスキーマに変換できます。たとえば、会社が使用するメッセージを取引先が使用するスキーマに変換できます。</span><span class="sxs-lookup"><span data-stu-id="58969-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="58969-105">マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信された応答メッセージに XSL 変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="58969-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="58969-106">出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="58969-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="58969-107">受信ポートに複数のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="58969-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="58969-108">マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="58969-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58969-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="58969-109">Prerequisites</span></span>  
 <span data-ttu-id="58969-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58969-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="58969-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="58969-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="58969-112">受信ポートの送信マップを構成するには</span><span class="sxs-lookup"><span data-stu-id="58969-112">To configure outbound maps for a receive port</span></span>  
  
1.  <span data-ttu-id="58969-113">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="58969-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="58969-114">コンソール ツリーで、BizTalk グループを展開し、受信ポートの送信マップを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="58969-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3.  <span data-ttu-id="58969-115">展開**受信ポート**受信ポートを右クリックしをクリックして**プロパティ**、順にクリック**送信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="58969-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4.  <span data-ttu-id="58969-116">次の表の説明に従って、送信マップを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="58969-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="58969-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58969-117">Use this</span></span>|<span data-ttu-id="58969-118">目的</span><span class="sxs-lookup"><span data-stu-id="58969-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="58969-119">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="58969-119">**Remove**</span></span>|<span data-ttu-id="58969-120">選択したマップを削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="58969-120">Click to remove the selected map.</span></span>|  
    |<span data-ttu-id="58969-121">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="58969-121">**Source Document**</span></span>|<span data-ttu-id="58969-122">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="58969-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="58969-123">**マップ**</span><span class="sxs-lookup"><span data-stu-id="58969-123">**Map**</span></span>|<span data-ttu-id="58969-124">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="58969-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="58969-125">**対象のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="58969-125">**Target Document**</span></span>|<span data-ttu-id="58969-126">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="58969-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58969-127">参照</span><span class="sxs-lookup"><span data-stu-id="58969-127">See Also</span></span>  
 <span data-ttu-id="58969-128">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="58969-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="58969-129">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="58969-129">Managing Maps</span></span>](../core/managing-maps.md)