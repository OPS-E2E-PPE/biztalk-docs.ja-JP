---
title: 新しいメッセージの公開を無効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2c46be41fa8dda72e849f756a487b89552621b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974139"
---
# <a name="disable-new-message-publication"></a><span data-ttu-id="55435-102">新しいメッセージの公開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="55435-102">Disable New Message Publication</span></span>

## <a name="overview"></a><span data-ttu-id="55435-103">概要</span><span class="sxs-lookup"><span data-stu-id="55435-103">Overview</span></span>
<span data-ttu-id="55435-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、新しいメッセージの公開を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="55435-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console or Windows Management Instrumentation (WMI) to disable new message publication.</span></span> <span data-ttu-id="55435-105">メッセージ ボックス データベースで新しいメッセージの受信を停止するには、メッセージ ボックス データベースの新しいメッセージの公開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="55435-105">You disable new message publication in the MessageBox database to stop the receipt of new messages by the MessageBox database.</span></span> <span data-ttu-id="55435-106">BizTalk Server 環境によっては、マスター メッセージ ボックス データベースの新しいメッセージの公開を無効にすると、パフォーマンスが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="55435-106">In some BizTalk Server environments, you can improve performance if you disable new message publication for the master MessageBox database.</span></span> <span data-ttu-id="55435-107">新しいメッセージの公開を無効にしても、メッセージ ボックス データベース内の既存のメッセージや処理中のサービス インスタンスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="55435-107">Disabling new message publication does not affect existing messages in the MessageBox database or service instances that are in progress.</span></span>  
  
 <span data-ttu-id="55435-108">WMI を使用して、新しいメッセージの公開を無効にする方法については、、 **MSBTS_MsgBoxSetting.DisableNewMessagePublication プロパティ (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55435-108">For information about using WMI to disable new message publication, see the **MSBTS_MsgBoxSetting.DisableNewMessagePublication Property (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="55435-109">メッセージ ボックス データベースを削除する前に、新しいメッセージの公開を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55435-109">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="55435-110">メッセージ ボックス データベースを削除する方法の詳細については、[メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55435-110">For information about deleting a MessageBox database, see [How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55435-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="55435-111">Prerequisites</span></span>  
 <span data-ttu-id="55435-112">メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="55435-112">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="55435-113">メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="55435-113">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="55435-114">BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55435-114">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="55435-115">データベースが存在するコンピューターの SQL Server 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="55435-115">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
## <a name="disable-steps"></a><span data-ttu-id="55435-116">手順を無効にします。</span><span class="sxs-lookup"><span data-stu-id="55435-116">Disable steps</span></span>
  
1. <span data-ttu-id="55435-117">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="55435-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="55435-118">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**メッセージ ボックス**します。</span><span class="sxs-lookup"><span data-stu-id="55435-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="55435-119">詳細ウィンドウで、無効にするをクリックするメッセージ ボックス データベースを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="55435-119">In the details pane, right-click the MessageBox database you want to disable, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="55435-120">**メッセージ ボックスのプロパティ**ダイアログ ボックスで、**新しいメッセージの公開を無効にする**チェック ボックスをオンにし**OK**。</span><span class="sxs-lookup"><span data-stu-id="55435-120">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55435-121">参照</span><span class="sxs-lookup"><span data-stu-id="55435-121">See Also</span></span>  
 <span data-ttu-id="55435-122">[メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="55435-122">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="55435-123">[メッセージ ボックス データベースを追加します。](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="55435-123">[Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="55435-124">[メッセージ ボックス データベースを削除します。](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="55435-124">[Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 [<span data-ttu-id="55435-125">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="55435-125">The MessageBox Database</span></span>](../core/the-messagebox-database.md)