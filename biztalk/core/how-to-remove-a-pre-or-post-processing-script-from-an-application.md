---
title: 処理前または処理後のスクリプトをアプリケーションから削除する方法 |Microsoft Docs
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
ms.openlocfilehash: 4af32e7aa3edae39fb43c1bf884c97ec376c7acf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384380"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a><span data-ttu-id="65bd4-102">処理前または処理後のスクリプトをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="65bd4-102">How to Remove a Pre- or Post-processing Script from an Application</span></span>
<span data-ttu-id="65bd4-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して、アプリケーションからの前または処理後のスクリプトを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove a pre- or post-processing script from an application.</span></span> <span data-ttu-id="65bd4-104">BizTalk 管理データベースからスクリプトをアプリケーションの .msi ファイルにエクスポートされませんようにこの削除します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-104">This removes the script from the BizTalk Management database, so that it will not be exported in the application .msi file.</span></span> <span data-ttu-id="65bd4-105">存在する場合、ローカル ファイル システムからスクリプトこの削除されません。</span><span class="sxs-lookup"><span data-stu-id="65bd4-105">This does not remove the script from the local file system, if it exists there.</span></span>  
  
 <span data-ttu-id="65bd4-106">スクリプトが含まれるアプリケーションが、ローカル ファイル システムにインストールされ、スクリプトがアンインストール中に実行するように設計場合、は、アプリケーションのアンインストール時に実行を防ぐために、ファイル システムからスクリプトを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65bd4-106">If the application containing the script has been installed on the local file system, and the script is designed to run during uninstallation, you must remove the script from the file system to prevent it from running when the application is uninstalled.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="65bd4-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="65bd4-107">Prerequisites</span></span>  
 <span data-ttu-id="65bd4-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65bd4-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="65bd4-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-script-from-an-application"></a><span data-ttu-id="65bd4-110">アプリケーションからのスクリプトを削除するには</span><span class="sxs-lookup"><span data-stu-id="65bd4-110">To remove a script from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="65bd4-111">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="65bd4-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="65bd4-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="65bd4-113">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、削除するには、スクリプトが含まれる BizTalk グループを展開し、スクリプトが含まれるアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to remove, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="65bd4-114">をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**削除**します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-114">Click the **Resources** folder, right-click the script, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="65bd4-115">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="65bd4-115">Using the command line</span></span>  
  
1. <span data-ttu-id="65bd4-116">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="65bd4-116">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="65bd4-117">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-117">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="65bd4-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="65bd4-118">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="65bd4-119">例:</span><span class="sxs-lookup"><span data-stu-id="65bd4-119">Example:</span></span>  
  
    <span data-ttu-id="65bd4-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span><span class="sxs-lookup"><span data-stu-id="65bd4-120">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**</span></span>  
  
   |<span data-ttu-id="65bd4-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65bd4-121">Parameter</span></span>|<span data-ttu-id="65bd4-122">説明</span><span class="sxs-lookup"><span data-stu-id="65bd4-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="65bd4-123">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="65bd4-123">**/ApplicationName**</span></span>|<span data-ttu-id="65bd4-124">削除する BizTalk スクリプトが含まれる BizTalk アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="65bd4-124">Name of the BizTalk application containing the BizTalk script to delete.</span></span> <span data-ttu-id="65bd4-125">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="65bd4-125">If the name includes spaces, it must be enclosed in double quotation marks (").</span></span> <span data-ttu-id="65bd4-126">このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="65bd4-126">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="65bd4-127">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="65bd4-127">**/Luid**</span></span>|<span data-ttu-id="65bd4-128">スクリプトのローカルで一意の識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="65bd4-128">Locally unique identifier (LUID) of the script.</span></span> <span data-ttu-id="65bd4-129">LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-129">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="65bd4-130">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="65bd4-130">**/Server**</span></span>|<span data-ttu-id="65bd4-131">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="65bd4-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="65bd4-132">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="65bd4-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="65bd4-133">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="65bd4-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="65bd4-134">例 :</span><span class="sxs-lookup"><span data-stu-id="65bd4-134">Examples:</span></span><br /><br /> <span data-ttu-id="65bd4-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="65bd4-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="65bd4-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="65bd4-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="65bd4-137">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="65bd4-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="65bd4-138">**/Database**</span><span class="sxs-lookup"><span data-stu-id="65bd4-138">**/Database**</span></span>|<span data-ttu-id="65bd4-139">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="65bd4-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="65bd4-140">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="65bd4-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65bd4-141">参照</span><span class="sxs-lookup"><span data-stu-id="65bd4-141">See Also</span></span>  
 <span data-ttu-id="65bd4-142">[前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="65bd4-142">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 [<span data-ttu-id="65bd4-143">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="65bd4-143">RemoveResource Command</span></span>](../core/removeresource-command.md)