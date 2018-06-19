---
title: スキーマの追跡を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15cb2210062901786b179ec75fe3880dea660b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248050"
---
# <a name="how-to-configure-tracking-for-a-schema"></a><span data-ttu-id="1b86f-102">スキーマの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1b86f-102">How to Configure Tracking for a Schema</span></span>
<span data-ttu-id="1b86f-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、スキーマの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b86f-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a schema.</span></span> <span data-ttu-id="1b86f-104">追跡を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [グループ ハブ] ページのクエリ ビューで、表示するメッセージのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b86f-104">To configure tracking, you specify the properties of the messages that you want to view in the query views of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="1b86f-105">詳細については、作成して、クエリを使用して、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="1b86f-106">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b86f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="1b86f-107">Prerequisites</span></span>  
 <span data-ttu-id="1b86f-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b86f-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="1b86f-109">追跡オプションを表示するだけの場合、BizTalk Server Operators グループのメンバーとしてログオンできます。</span><span class="sxs-lookup"><span data-stu-id="1b86f-109">To you want to view tracking options only, you can be logged on as a member of the BizTalk Server Operators group.</span></span> <span data-ttu-id="1b86f-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-schema"></a><span data-ttu-id="1b86f-111">スキーマの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="1b86f-111">To configure tracking for a schema</span></span>  
  
1.  <span data-ttu-id="1b86f-112">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1b86f-113">コンソール ツリーで  **BizTalk Server 管理コンソール**追跡を構成するスキーマが含まれる BizTalk グループを展開し、スキーマを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="1b86f-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to configure tracking, and then expand the application containing the schema.</span></span>  
  
3.  <span data-ttu-id="1b86f-114">をクリックして**スキーマ**、スキーマを右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-114">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1b86f-115">左側のウィンドウでをクリックして**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="1b86f-115">In the left pane, click **Tracking**.</span></span>  
  
5.  <span data-ttu-id="1b86f-116">クリックして、メッセージを追跡するために使用するプロパティを指定するには、次のいずれかの操作**OK**:</span><span class="sxs-lookup"><span data-stu-id="1b86f-116">Do one of the following to specify which properties to use for tracking messages, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="1b86f-117">選択、**すべてのメッセージ プロパティを選択して**示されているすべてのプロパティを使用する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="1b86f-117">Select the **Select all message properties** check box to use all the listed properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1b86f-118">このチェック ボックスは、昇格させたプロパティを含むスキーマに対してのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="1b86f-118">This check box is available only for schemas that contain promoted properties.</span></span>  
  
    -   <span data-ttu-id="1b86f-119">使用する各プロパティのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b86f-119">Select the check box of each property that you want to use.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1b86f-120">これは、昇格させたプロパティを含むスキーマに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b86f-120">This is available only for schemas that contain promoted properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b86f-121">メッセージの追跡によって、システムのパフォーマンスとストレージにオーバーヘッドが発生します。したがって、オプションは必要なもののみ選択してください。</span><span class="sxs-lookup"><span data-stu-id="1b86f-121">You should select only the options you need, as tracking messages creates performance and storage overhead for your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b86f-122">参照</span><span class="sxs-lookup"><span data-stu-id="1b86f-122">See Also</span></span>  
 [<span data-ttu-id="1b86f-123">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="1b86f-123">Managing Schemas</span></span>](../core/managing-schemas.md)