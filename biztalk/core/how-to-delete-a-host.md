---
title: ホストの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351311d526500529c293fffbd400a5c1d317ed16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385386"
---
# <a name="delete-a-host"></a><span data-ttu-id="0c262-102">ホストを削除します。</span><span class="sxs-lookup"><span data-stu-id="0c262-102">Delete a Host</span></span>
<span data-ttu-id="0c262-103">ホストは、以下の状況でのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="0c262-103">You can delete a host only in the following circumstances:</span></span>  

- <span data-ttu-id="0c262-104">既定のホストではない。</span><span class="sxs-lookup"><span data-stu-id="0c262-104">It is not the default host.</span></span>  

- <span data-ttu-id="0c262-105">ホスト追跡を行う唯一のホストではない。</span><span class="sxs-lookup"><span data-stu-id="0c262-105">It is not the only host that is performing host tracking.</span></span>  

- <span data-ttu-id="0c262-106">アダプター ハンドラーをホストしてない。</span><span class="sxs-lookup"><span data-stu-id="0c262-106">It is not hosting any adapter handlers.</span></span>  

- <span data-ttu-id="0c262-107">参加しているオーケストレーションがない。</span><span class="sxs-lookup"><span data-stu-id="0c262-107">It has no enlisted orchestrations.</span></span>  

- <span data-ttu-id="0c262-108">開始されているホスト インスタンスがない。</span><span class="sxs-lookup"><span data-stu-id="0c262-108">There are no started instances of the host.</span></span>  

- <span data-ttu-id="0c262-109">ホストがクラスター化されていない。</span><span class="sxs-lookup"><span data-stu-id="0c262-109">If the host is not clustered.</span></span>  

  <span data-ttu-id="0c262-110">ホストの詳細については、次を参照してください。[ホスト](../core/hosts.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c262-110">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0c262-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="0c262-111">Prerequisites</span></span>  
 <span data-ttu-id="0c262-112">ホストの作成、ホスト プロパティの変更、およびホストの削除には、次のユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c262-112">You must have the following user rights to create hosts, modify host properties, and delete hosts:</span></span>  

-   <span data-ttu-id="0c262-113">BizTalk Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c262-113">You must be a member of the BizTalk Server Administrators group.</span></span>  

-   <span data-ttu-id="0c262-114">SQL Server には次の権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c262-114">You must have the following rights in SQL Server:</span></span>  

    -   <span data-ttu-id="0c262-115">BizTalk 追跡データベース (BizTalk DTADb)、メッセージ ボックス データベース (BizTalkMsgBoxDb)、および BAM プライマリ インポート データベース (BAMPrimaryImport) では、SQL Server の管理者であるか、SQL Server データベース ロールの db_owner または db_securityadmin のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c262-115">You must be either a SQL Server administrator, or a member of the db_owner or db_securityadmin SQL Server database roles in the BizTalk Tracking database (BizTalk DTADb), MessageBox databases (BizTalkMsgBoxDb), and the BAM Primary Import database (BAMPrimaryImport).</span></span>  

    -   <span data-ttu-id="0c262-116">メッセージ ボックス データベースが存在するすべてのコンピューターの sysadmin SQL Server ロールのメンバーであるか、すべてのメッセージ ボックス データベースの db_owner または db_ddladmin SQL Server ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c262-116">You must be a member of the sysadmin SQL Server role on all the computers where there are MessageBox databases, or a member of the db_owner or db_ddladmin SQL Server role for all the MessageBox databases.</span></span>  

## <a name="steps"></a><span data-ttu-id="0c262-117">手順</span><span class="sxs-lookup"><span data-stu-id="0c262-117">Steps</span></span> 

1. <span data-ttu-id="0c262-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0c262-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="0c262-119">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="0c262-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Hosts**.</span></span>  

3. <span data-ttu-id="0c262-120">詳細ペインで、削除、およびクリックするホストを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="0c262-120">In the details pane, right-click the host you want to delete, and then click **Delete**.</span></span>  

4. <span data-ttu-id="0c262-121">**ホスト削除の確認**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="0c262-121">In the **Confirm host delete** dialog box, click **Yes**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0c262-122">参照</span><span class="sxs-lookup"><span data-stu-id="0c262-122">See Also</span></span>  
- [<span data-ttu-id="0c262-123">BizTalk ホストとホスト インスタンスの管理</span><span class="sxs-lookup"><span data-stu-id="0c262-123">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)   
- [<span data-ttu-id="0c262-124">新しいホストを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0c262-124">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)   
- [<span data-ttu-id="0c262-125">ホストのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="0c262-125">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)   
- <span data-ttu-id="0c262-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0c262-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
