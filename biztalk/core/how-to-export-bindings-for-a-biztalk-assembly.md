---
title: BizTalk アセンブリのバインドをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2807e0832dae1722e2b0b15e7b098246784bca88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337782"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a><span data-ttu-id="ae683-102">BizTalk アセンブリのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="ae683-102">How to Export Bindings for a BizTalk Assembly</span></span>
<span data-ttu-id="ae683-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk アセンブリのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae683-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk assembly to an .xml file.</span></span> <span data-ttu-id="ae683-104">エクスポートしたバインドは、BizTalk アプリケーションにインポートできます。この際、既存のバインドにインポートするバインドと同じ名前が含まれている場合は、既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ae683-104">You can then import these bindings into a BizTalk application, which overwrites existing bindings with the imported bindings of the same name.</span></span> <span data-ttu-id="ae683-105">アセンブリを更新する前にバインドをエクスポートしておくと、更新後にインポートすることでバインドを再適用できます。</span><span class="sxs-lookup"><span data-stu-id="ae683-105">You might want to export the bindings for an assembly before you update it, so that you can import the bindings after you update it to reapply them.</span></span> <span data-ttu-id="ae683-106">アプリケーションとアセンブリの更新の詳細については、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae683-106">For more information about updating applications and assemblies, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span> <span data-ttu-id="ae683-107">バインド ファイルの使用についての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae683-107">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ae683-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="ae683-108">Prerequisites</span></span>  
 <span data-ttu-id="ae683-109">このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae683-109">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Server Operators group.</span></span> <span data-ttu-id="ae683-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae683-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a><span data-ttu-id="ae683-111">BizTalk アセンブリのバインドをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ae683-111">To export bindings for a BizTalk assembly</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="ae683-112">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="ae683-112">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="ae683-113">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="ae683-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ae683-114">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="ae683-114">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3. <span data-ttu-id="ae683-115">アセンブリを含むアプリケーションを右クリックし、[**エクスポート**、] をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="ae683-115">Right-click the application containing the assembly, point to **Export**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="ae683-116">バインドのエクスポート ページで**ファイルにエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae683-116">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="ae683-117">例:**C:\Bindings\MyAssemblyBindings_Staging1.xml**</span><span class="sxs-lookup"><span data-stu-id="ae683-117">Example: **C:\Bindings\MyAssemblyBindings_Staging1.xml**</span></span>  
  
5. <span data-ttu-id="ae683-118">バインドのエクスポート] ページで、次のようにクリックします。**選択したアセンブリのバインドをエクスポート**、し、[**アセンブリ**、アセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae683-118">On the Export Bindings page, click **Export bindings for the selected assembly**, and then in **Assembly**, click the assembly.</span></span>  
  
6. <span data-ttu-id="ae683-119">すべてのグループのパーティ情報をエクスポートする場合は、選択**グローバル パーティ情報をエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="ae683-119">If you want to export all of the party information in the group, select **Export Global Party Information**.</span></span>  
  
    <span data-ttu-id="ae683-120">指定した場所の .xml ファイルに、バインドがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae683-120">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="ae683-121">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="ae683-121">Using the command line</span></span>  
  
1. <span data-ttu-id="ae683-122">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ae683-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ae683-123">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae683-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="ae683-124">**BTSTask ExportBindings /Destination:** *value* **/AssemblyName:** *value* **[/GlobalParties]** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="ae683-124">**BTSTask ExportBindings /Destination:** *value* **/AssemblyName:** *value* [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="ae683-125">例:</span><span class="sxs-lookup"><span data-stu-id="ae683-125">Example:</span></span>  
  
    <span data-ttu-id="ae683-126">**BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 11e921d58826420e"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="ae683-126">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /AssemblyName:"ErrorHandling.ErrorHandler, Version=1.0.0.0, Culture=neutral, PublicKeyToken=11e921d58826420e" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="ae683-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae683-127">Parameter</span></span>|<span data-ttu-id="ae683-128">値</span><span class="sxs-lookup"><span data-stu-id="ae683-128">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="ae683-129">**/変換先**</span><span class="sxs-lookup"><span data-stu-id="ae683-129">**/Destination**</span></span>|<span data-ttu-id="ae683-130">作成するバインド ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="ae683-130">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="ae683-131">同じパスの既存のバインド ファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ae683-131">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="ae683-132">パスにスペースがある場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae683-132">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="ae683-133">**/AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="ae683-133">**/AssemblyName**</span></span>|<span data-ttu-id="ae683-134">バインドのエクスポート元となるアセンブリのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="ae683-134">Locally unique identifier (LUID) of the assembly from which to export bindings.</span></span> <span data-ttu-id="ae683-135">使用して、アプリケーションでのアイテムの Luid の一覧を取得することができます、 [ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae683-135">You can obtain a list of LUIDs for the artifacts in an application by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="ae683-136">**/GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="ae683-136">**/GlobalParties**</span></span>|<span data-ttu-id="ae683-137">指定した場合、グループのグローバル パーティ情報をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ae683-137">When specified, exports global pary information for the group.</span></span>|  
   |<span data-ttu-id="ae683-138">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="ae683-138">**/Server**</span></span>|<span data-ttu-id="ae683-139">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="ae683-139">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="ae683-140">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ae683-140">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="ae683-141">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ae683-141">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="ae683-142">例 :</span><span class="sxs-lookup"><span data-stu-id="ae683-142">Examples:</span></span><br /><br /> <span data-ttu-id="ae683-143">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="ae683-143">Server=MyServer</span></span><br /><br /> <span data-ttu-id="ae683-144">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="ae683-144">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="ae683-145">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae683-145">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="ae683-146">**/Database**</span><span class="sxs-lookup"><span data-stu-id="ae683-146">**/Database**</span></span>|<span data-ttu-id="ae683-147">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ae683-147">Name of the BizTalk Management database.</span></span> <span data-ttu-id="ae683-148">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae683-148">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae683-149">参照</span><span class="sxs-lookup"><span data-stu-id="ae683-149">See Also</span></span>  
 <span data-ttu-id="ae683-150">[バインドのエクスポート](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="ae683-150">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="ae683-151">[ExportBindings コマンド](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="ae683-151">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="ae683-152">BizTalk アプリケーション、バインド、およびポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="ae683-152">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)