---
title: 前または処理後のスクリプトをアプリケーションから削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d60bdec2857d9d84042e184f0bbfbb2307806a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254762"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a><span data-ttu-id="d2e71-102">処理前または処理後のスクリプトをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="d2e71-102">How to Remove a Pre- or Post-processing Script from an Application</span></span>
<span data-ttu-id="d2e71-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、処理前または処理後のスクリプトをアプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2e71-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove a pre- or post-processing script from an application.</span></span> <span data-ttu-id="d2e71-104">これにより、BizTalk 管理データベースからスクリプトが削除されます。そのため、アプリケーションの.msi ファイルにスクリプトがエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d2e71-104">This removes the script from the BizTalk Management database, so that it will not be exported in the application .msi file.</span></span> <span data-ttu-id="d2e71-105">ローカル ファイル システムに存在しているスクリプトは削除されません。</span><span class="sxs-lookup"><span data-stu-id="d2e71-105">This does not remove the script from the local file system, if it exists there.</span></span>  
  
 <span data-ttu-id="d2e71-106">スクリプトを含むアプリケーションをローカル ファイル システムにインストールし、このスクリプトがアンインストール中に実行される場合は、このスクリプトをファイルシステムから削除して、アプリケーションのアンインストール中に実行されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2e71-106">If the application containing the script has been installed on the local file system, and the script is designed to run during uninstallation, you must remove the script from the file system to prevent it from running when the application is uninstalled.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d2e71-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d2e71-107">Prerequisites</span></span>  
 <span data-ttu-id="d2e71-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2e71-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d2e71-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-script-from-an-application"></a><span data-ttu-id="d2e71-110">アプリケーションからスクリプトを削除するには</span><span class="sxs-lookup"><span data-stu-id="d2e71-110">To remove a script from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="d2e71-111">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="d2e71-111">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="d2e71-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d2e71-113">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、削除するスクリプトが含まれる BizTalk グループ、スクリプトが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="d2e71-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to remove, and then expand the application containing the script.</span></span>  
  
3.  <span data-ttu-id="d2e71-114">クリックして、**リソース**フォルダーは、スクリプトを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-114">Click the **Resources** folder, right-click the script, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="d2e71-115">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="d2e71-115">Using the command line</span></span>  
  
1.  <span data-ttu-id="d2e71-116">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-116">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d2e71-117">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2e71-117">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="d2e71-118">**BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]</span><span class="sxs-lookup"><span data-stu-id="d2e71-118">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="d2e71-119">例:</span><span class="sxs-lookup"><span data-stu-id="d2e71-119">Example:</span></span>  
  
     <span data-ttu-id="d2e71-120">**BTSTask RemoveResource applicationname: myapplication/Luid:"MyApplication:MyScript.vbs"**</span><span class="sxs-lookup"><span data-stu-id="d2e71-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span></span>  
  
    |<span data-ttu-id="d2e71-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2e71-121">Parameter</span></span>|<span data-ttu-id="d2e71-122">Description</span><span class="sxs-lookup"><span data-stu-id="d2e71-122">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d2e71-123">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="d2e71-123">**/ApplicationName**</span></span>|<span data-ttu-id="d2e71-124">削除する BizTalk スクリプトが存在する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="d2e71-124">Name of the BizTalk application containing the BizTalk script to delete.</span></span> <span data-ttu-id="d2e71-125">名前にスペースが含まれる場合は、名前を二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2e71-125">If the name includes spaces, it must be enclosed in double quotation marks (").</span></span> <span data-ttu-id="d2e71-126">このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2e71-126">If this parameter is not specified, the default application is used.</span></span>|  
    |<span data-ttu-id="d2e71-127">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="d2e71-127">**/Luid**</span></span>|<span data-ttu-id="d2e71-128">スクリプトのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="d2e71-128">Locally unique identifier (LUID) of the script.</span></span> <span data-ttu-id="d2e71-129">使用して、LUID を取得することができます、 [ListApp コマンド](../core/listapp-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-129">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="d2e71-130">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="d2e71-130">**/Server**</span></span>|<span data-ttu-id="d2e71-131">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="d2e71-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="d2e71-132">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="d2e71-133">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="d2e71-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="d2e71-134">例 :</span><span class="sxs-lookup"><span data-stu-id="d2e71-134">Examples:</span></span><br /><br /> <span data-ttu-id="d2e71-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="d2e71-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="d2e71-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="d2e71-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="d2e71-137">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2e71-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="d2e71-138">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="d2e71-138">**/Database**</span></span>|<span data-ttu-id="d2e71-139">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="d2e71-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="d2e71-140">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2e71-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2e71-141">参照</span><span class="sxs-lookup"><span data-stu-id="d2e71-141">See Also</span></span>  
 <span data-ttu-id="d2e71-142">[前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="d2e71-142">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 [<span data-ttu-id="d2e71-143">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="d2e71-143">RemoveResource Command</span></span>](../core/removeresource-command.md)