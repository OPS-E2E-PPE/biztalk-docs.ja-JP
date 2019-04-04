---
title: 既定のアプリケーションを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4122b7ab0581be974ee1fdd38ba2cc3ddbc41e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986555"
---
# <a name="how-to-change-the-default-application"></a><span data-ttu-id="77860-102">既定のアプリケーションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="77860-102">How to Change the Default Application</span></span>
<span data-ttu-id="77860-103">このトピックでは、BizTalk Server 管理コンソールでアプリケーションのプロパティを編集することにより、既定のアプリケーションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77860-103">This topic describes how to change the default application by editing the properties of an application in the BizTalk Server Administration console.</span></span> <span data-ttu-id="77860-104">」の説明に従って、新しいアプリケーションを作成して、既定のアプリケーションとして指定することで、既定のアプリケーションに変更することもできます[アプリケーションを作成する方法](../core/how-to-create-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="77860-104">You can also change the default application by creating a new application and specifying it as the default application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="77860-105">BizTalk Server をインストールすると、BizTalk Application 1 という名前の既定のアプリケーションが BizTalk 管理データベースに作成されて、BizTalk Server 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="77860-105">When you install BizTalk Server, a default application named BizTalk Application 1 is created in the BizTalk Management database and appears in the BizTalk Server Administration console.</span></span> <span data-ttu-id="77860-106">BizTalk Server を以前のバージョンからアップグレードすると、アイテムが自動的にこのアプリケーション内に置かれます。</span><span class="sxs-lookup"><span data-stu-id="77860-106">When you upgrade from an earlier version of BizTalk Server, your artifacts are automatically placed in this application.</span></span> <span data-ttu-id="77860-107">また、BTSTask でアプリケーションを指定せずに Windows インストーラー (.msi) ファイルをインポートすると、.msi ファイルが既定のアプリケーションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="77860-107">In addition, when you import a Windows Installer (.msi) file by using BTSTask without specifying an application, the artifacts in the .msi file are imported into the default application.</span></span>  
  
 <span data-ttu-id="77860-108">既定のアプリケーションは削除できませんが、どのアプリケーションを既定とするかは変更できます。</span><span class="sxs-lookup"><span data-stu-id="77860-108">You cannot delete the default application; however, you can change which application is the default.</span></span> <span data-ttu-id="77860-109">既定のアプリケーションを変更したら、必要に応じて、以前に既定であったアプリケーションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="77860-109">If you change the default application, you can then delete the application that was previously the default, if you want.</span></span> <span data-ttu-id="77860-110">手順については、[BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77860-110">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="77860-111">既定のアプリケーションを変更しても、アイテムはすべて、以前に既定であったアプリケーション内に残ります。</span><span class="sxs-lookup"><span data-stu-id="77860-111">When you change the default application, all of the artifacts remain in the application that was originally the default.</span></span> <span data-ttu-id="77860-112">必要に応じて、アプリケーションからアイテムを明示的に移動できます。</span><span class="sxs-lookup"><span data-stu-id="77860-112">You can explicitly move the artifacts out of the application, if you want.</span></span> <span data-ttu-id="77860-113">手順については、[を別のアプリケーション アイテムの移動方法](../core/how-to-move-an-artifact-to-a-different-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77860-113">For instructions, see [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="77860-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="77860-114">Prerequisites</span></span>  
 <span data-ttu-id="77860-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77860-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="77860-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="77860-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-default-application"></a><span data-ttu-id="77860-117">既定のアプリケーションを変更するには</span><span class="sxs-lookup"><span data-stu-id="77860-117">To change the default application</span></span>  
  
1. <span data-ttu-id="77860-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="77860-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="77860-119">コンソール ツリーで、展開**BizTalk Server 管理**を BizTalk グループを展開し、アプリケーションが既定の設定 をクリックするを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="77860-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, right-click the application that you want to make the default, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="77860-120">選択、 **、既定のアプリケーションをこのように**チェック ボックスをオンにして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="77860-120">Select the **Make this the default application** check box, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77860-121">参照</span><span class="sxs-lookup"><span data-stu-id="77860-121">See Also</span></span>  
 [<span data-ttu-id="77860-122">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="77860-122">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)