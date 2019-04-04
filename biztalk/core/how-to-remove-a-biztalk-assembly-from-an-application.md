---
title: アプリケーションから BizTalk アセンブリを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], assemblies
- assemblies, deleting
- deleting, assemblies
- applications, assemblies
- managing [assemblies], deleting
ms.assetid: 0691c3b6-476d-4e01-b50b-47d7c0b299bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0865c55480710e52c4d4d87d444d35ac48f0dd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987835"
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a><span data-ttu-id="e4479-102">BizTalk アセンブリをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="e4479-102">How to Remove a BizTalk Assembly from an Application</span></span>
<span data-ttu-id="e4479-103">ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アセンブリを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4479-103">This topic describes how use the BizTalk Server Administration console or the command line to remove a BizTalk assembly from a BizTalk application.</span></span> <span data-ttu-id="e4479-104">この操作を実行すると、アセンブリおよびそのアセンブリに含まれるアイテム (オーケストレーション、スキーマ、パイプラインなど) は、アプリケーションおよび BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e4479-104">When you do this, the assembly and the artifacts that it includes, such as orchestrations, schemas, and pipelines, are removed from the application and the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="e4479-105">BizTalk アセンブリを削除する前に、次の重要事項を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e4479-105">Before removing a BizTalk assembly, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="e4479-106">BizTalk アセンブリを削除すると、アセンブリ ファイルは、グローバル アセンブリ キャッシュ (GAC) またはローカル ファイル システム内に存在する場合、自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="e4479-106">When you remove a BizTalk assembly, the assembly file is not automatically removed from the global assembly cache (GAC) or the local file system, if it exists there.</span></span> <span data-ttu-id="e4479-107">そのアセンブリ ファイルは手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4479-107">You must manually remove it.</span></span> <span data-ttu-id="e4479-108">手順については、[GAC からアセンブリをアンインストールする方法](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)と[BizTalk アプリケーションの設定およびその他のファイルを削除する方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4479-108">For instructions, see [How to Uninstall an Assembly from the GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4) and [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="e4479-109">パイプラインを含む BizTalk アセンブリを削除すると、同じアプリケーション内でそのパイプラインを使用する送信ポートはすべてリセットされて、既定の PassThruTransmit パイプラインを使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="e4479-109">If you remove a BizTalk assembly that includes a pipeline, any send ports in the same application that use the pipeline will be reset to use the default, PassThruTransmit pipeline.</span></span>  
  
-   <span data-ttu-id="e4479-110">他のアイテムが依存する BizTalk アセンブリは削除できません。</span><span class="sxs-lookup"><span data-stu-id="e4479-110">You cannot remove a BizTalk assembly on which other artifacts depend.</span></span> <span data-ttu-id="e4479-111">最初に、依存関係にあるアイテムを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4479-111">You must first remove the dependent artifacts.</span></span> <span data-ttu-id="e4479-112">それから、BizTalk アセンブリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e4479-112">Then you can remove the BizTalk assembly.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4479-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="e4479-113">Prerequisites</span></span>  
 <span data-ttu-id="e4479-114">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4479-114">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e4479-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4479-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a><span data-ttu-id="e4479-116">アプリケーションから BizTalk アセンブリを削除するには</span><span class="sxs-lookup"><span data-stu-id="e4479-116">To remove a BizTalk assembly from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="e4479-117">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="e4479-117">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="e4479-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="e4479-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e4479-119">コンソール ツリーで BizTalk Server 管理コンソールを展開しを削除する BizTalk アセンブリが含まれる BizTalk グループを展開し、BizTalk アセンブリを格納しているアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e4479-119">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly to remove, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="e4479-120">をクリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、順にクリックします**削除**します。</span><span class="sxs-lookup"><span data-stu-id="e4479-120">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="e4479-121">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="e4479-121">Using the command line</span></span>  
  
1. <span data-ttu-id="e4479-122">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e4479-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e4479-123">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4479-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="e4479-124">**BTSTask RemoveResource** [**/applicationname は:**<em>値</em>] **/Luid:**<em>値</em>[**/Server:** <em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="e4479-124">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="e4479-125">例:</span><span class="sxs-lookup"><span data-stu-id="e4479-125">Example:</span></span>  
  
    <span data-ttu-id="e4479-126">**BTSTask RemoveResource applicationname: myapplication/Luid:"MyApp.Orchestrations、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="e4479-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
   |<span data-ttu-id="e4479-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4479-127">Parameter</span></span>|<span data-ttu-id="e4479-128">説明</span><span class="sxs-lookup"><span data-stu-id="e4479-128">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="e4479-129">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="e4479-129">**/ApplicationName**</span></span>|<span data-ttu-id="e4479-130">削除する BizTalk アセンブリが含まれる BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="e4479-130">Name of the BizTalk application containing the BizTalk assembly to delete.</span></span> <span data-ttu-id="e4479-131">このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4479-131">If this parameter is not specified, the default application is used.</span></span> <span data-ttu-id="e4479-132">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4479-132">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="e4479-133">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="e4479-133">**/Luid**</span></span>|<span data-ttu-id="e4479-134">BizTalk アセンブリのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="e4479-134">Locally unique identifier (LUID) of the BizTalk assembly.</span></span> <span data-ttu-id="e4479-135">LUID を取得するにを使用して、 **ListApp** 」の説明に従って、コマンド[ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4479-135">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="e4479-136">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="e4479-136">**/Server**</span></span>|<span data-ttu-id="e4479-137">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="e4479-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="e4479-138">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="e4479-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="e4479-139">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="e4479-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="e4479-140">例 :</span><span class="sxs-lookup"><span data-stu-id="e4479-140">Examples:</span></span><br /><br /> <span data-ttu-id="e4479-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="e4479-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="e4479-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="e4479-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="e4479-143">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4479-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="e4479-144">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="e4479-144">**/Database**</span></span>|<span data-ttu-id="e4479-145">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e4479-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="e4479-146">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4479-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4479-147">参照</span><span class="sxs-lookup"><span data-stu-id="e4479-147">See Also</span></span>  
 <span data-ttu-id="e4479-148">[BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="e4479-148">[Managing BizTalk Assemblies](../core/managing-biztalk-assemblies.md) </span></span>  
 [<span data-ttu-id="e4479-149">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="e4479-149">RemoveResource Command</span></span>](../core/removeresource-command.md)