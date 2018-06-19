---
title: 既定のアプリケーションを変更する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 33b4ffb6fbbb2463b20a7d344d0f7f27811de23b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247986"
---
# <a name="how-to-change-the-default-application"></a><span data-ttu-id="ca914-102">既定のアプリケーションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="ca914-102">How to Change the Default Application</span></span>
<span data-ttu-id="ca914-103">このトピックでは、BizTalk Server 管理コンソールでアプリケーションのプロパティを編集することにより、既定のアプリケーションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca914-103">This topic describes how to change the default application by editing the properties of an application in the BizTalk Server Administration console.</span></span> <span data-ttu-id="ca914-104">」の説明に従って、新しいアプリケーションを作成して、既定のアプリケーションとして指定することで、既定のアプリケーションに変更することもできます[アプリケーションを作成する方法](../core/how-to-create-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca914-104">You can also change the default application by creating a new application and specifying it as the default application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="ca914-105">BizTalk Server をインストールすると、BizTalk Application 1 という名前の既定のアプリケーションが BizTalk 管理データベースに作成されて、BizTalk Server 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca914-105">When you install BizTalk Server, a default application named BizTalk Application 1 is created in the BizTalk Management database and appears in the BizTalk Server Administration console.</span></span> <span data-ttu-id="ca914-106">BizTalk Server を以前のバージョンからアップグレードすると、アイテムが自動的にこのアプリケーション内に置かれます。</span><span class="sxs-lookup"><span data-stu-id="ca914-106">When you upgrade from an earlier version of BizTalk Server, your artifacts are automatically placed in this application.</span></span> <span data-ttu-id="ca914-107">また、BTSTask でアプリケーションを指定せずに Windows インストーラー (.msi) ファイルをインポートすると、.msi ファイルが既定のアプリケーションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca914-107">In addition, when you import a Windows Installer (.msi) file by using BTSTask without specifying an application, the artifacts in the .msi file are imported into the default application.</span></span>  
  
 <span data-ttu-id="ca914-108">既定のアプリケーションは削除できませんが、どのアプリケーションを既定とするかは変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca914-108">You cannot delete the default application; however, you can change which application is the default.</span></span> <span data-ttu-id="ca914-109">既定のアプリケーションを変更したら、必要に応じて、以前に既定であったアプリケーションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="ca914-109">If you change the default application, you can then delete the application that was previously the default, if you want.</span></span> <span data-ttu-id="ca914-110">手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca914-110">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="ca914-111">既定のアプリケーションを変更しても、アイテムはすべて、以前に既定であったアプリケーション内に残ります。</span><span class="sxs-lookup"><span data-stu-id="ca914-111">When you change the default application, all of the artifacts remain in the application that was originally the default.</span></span> <span data-ttu-id="ca914-112">必要に応じて、アプリケーションからアイテムを明示的に移動できます。</span><span class="sxs-lookup"><span data-stu-id="ca914-112">You can explicitly move the artifacts out of the application, if you want.</span></span> <span data-ttu-id="ca914-113">手順については、次を参照してください。[別のアプリケーションにアイテムを移動する方法](../core/how-to-move-an-artifact-to-a-different-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca914-113">For instructions, see [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca914-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca914-114">Prerequisites</span></span>  
 <span data-ttu-id="ca914-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca914-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ca914-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca914-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-default-application"></a><span data-ttu-id="ca914-117">既定のアプリケーションを変更するには</span><span class="sxs-lookup"><span data-stu-id="ca914-117">To change the default application</span></span>  
  
1.  <span data-ttu-id="ca914-118">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ca914-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ca914-119">コンソール ツリーで  **BizTalk Server 管理コンソール**を BizTalk グループを展開し、クリックして、既定にするアプリケーションを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ca914-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, right-click the application that you want to make the default, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ca914-120">選択、**しやすいように、既定のアプリケーション**チェック ボックスをオンし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ca914-120">Select the **Make this the default application** check box, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca914-121">参照</span><span class="sxs-lookup"><span data-stu-id="ca914-121">See Also</span></span>  
 [<span data-ttu-id="ca914-122">作成して、BizTalk アプリケーションの変更</span><span class="sxs-lookup"><span data-stu-id="ca914-122">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)