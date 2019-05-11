---
title: BizTalk アプリケーションのバインドをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exportings
- applications, exporting
- applications, bindings
ms.assetid: 700d2781-480b-42ed-a313-1a67a7406369
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6750ff2f6684942c20eb4fdaa286dcbc181bb5b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385049"
---
# <a name="how-to-export-bindings-for-a-biztalk-application"></a><span data-ttu-id="a2739-102">BizTalk アプリケーションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="a2739-102">How to Export Bindings for a BizTalk Application</span></span>
<span data-ttu-id="a2739-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2739-103">This topic describes how to use the BizTalk Server Administration console or the command line export the bindings for a BizTalk application to an .xml file.</span></span> <span data-ttu-id="a2739-104">その後、バインド ファイルを別のアプリケーションにインポートすることで、アプリケーションの現在のバインドが、インポートした同じ名前のバインドで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a2739-104">You can then import the binding file into another application, which overwrites the current bindings in the application with the imported bindings of the same name.</span></span> <span data-ttu-id="a2739-105">詳細については、次を参照してください。 [BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2739-105">For more information, see [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="a2739-106">バインド ファイルの使用についての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2739-106">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2739-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a2739-107">Prerequisites</span></span>  
 <span data-ttu-id="a2739-108">このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2739-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Server Operators group.</span></span> <span data-ttu-id="a2739-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2739-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-application"></a><span data-ttu-id="a2739-110">BizTalk アプリケーションのバインドをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a2739-110">To export bindings for a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a2739-111">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="a2739-111">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="a2739-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a2739-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a2739-113">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、展開、**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a2739-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="a2739-114">エクスポートするバインドをポイントして、アプリケーションを右クリックして**エクスポート**、 をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="a2739-114">Right-click the application whose bindings you want to export, point to **Export**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="a2739-115">バインドのエクスポート ページで**ファイルにエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2739-115">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="a2739-116">例:**C:\Bindings\Application1Bindings_Staging1.xml**</span><span class="sxs-lookup"><span data-stu-id="a2739-116">Example: **C:\Bindings\Application1Bindings_Staging1.xml**</span></span>  
  
5. <span data-ttu-id="a2739-117">いることを確認 **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されているし、をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="a2739-117">Ensure that **Export all bindings from the current application** is selected, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="a2739-118">グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a2739-118">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
    <span data-ttu-id="a2739-119">バインドは、指定した場所の .xml ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a2739-119">The bindings are exported into an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a2739-120">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="a2739-120">Using the command line</span></span>  
  
1. <span data-ttu-id="a2739-121">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="a2739-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a2739-122">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2739-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="a2739-123">**BTSTask ExportBindings /Destination:** *value* [**/ApplicationName:**<em>value</em>] **[/GlobalParties]** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="a2739-123">**BTSTask ExportBindings /Destination:** *value* [**/ApplicationName:**<em>value</em>] [**/GlobalParties**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="a2739-124">例:</span><span class="sxs-lookup"><span data-stu-id="a2739-124">Example:</span></span>  
  
    <span data-ttu-id="a2739-125">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="a2739-125">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="a2739-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2739-126">Parameter</span></span>|<span data-ttu-id="a2739-127">値</span><span class="sxs-lookup"><span data-stu-id="a2739-127">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="a2739-128">**/変換先**</span><span class="sxs-lookup"><span data-stu-id="a2739-128">**/Destination**</span></span>|<span data-ttu-id="a2739-129">作成するバインド ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="a2739-129">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="a2739-130">同じパスの既存のバインド ファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a2739-130">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="a2739-131">パスにスペースがある場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2739-131">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="a2739-132">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="a2739-132">**/ApplicationName**</span></span>|<span data-ttu-id="a2739-133">バインドのエクスポート元のアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="a2739-133">Name of the application from which to export bindings.</span></span> <span data-ttu-id="a2739-134">アプリケーションが存在していることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a2739-134">The application must exist.</span></span> <span data-ttu-id="a2739-135">アプリケーション名を確認するには、使用することができます、 **ListApps** 」の説明に従って、コマンド[ListApps コマンド](../core/listapps-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2739-135">To verify the application name, you can use the **ListApps** command, as described in [ListApps Command](../core/listapps-command.md).</span></span> <span data-ttu-id="a2739-136">このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2739-136">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="a2739-137">名前にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2739-137">If there are spaces in the name, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="a2739-138">**/GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="a2739-138">**/GlobalParties**</span></span>|<span data-ttu-id="a2739-139">指定した場合、グループのグローバル パーティ情報をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a2739-139">When specified, exports global party information for the group.</span></span>|  
   |<span data-ttu-id="a2739-140">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="a2739-140">**/Server**</span></span>|<span data-ttu-id="a2739-141">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a2739-141">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="a2739-142">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2739-142">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="a2739-143">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2739-143">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="a2739-144">例 :</span><span class="sxs-lookup"><span data-stu-id="a2739-144">Examples:</span></span><br /><br /> <span data-ttu-id="a2739-145">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="a2739-145">Server=MyServer</span></span><br /><br /> <span data-ttu-id="a2739-146">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="a2739-146">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="a2739-147">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2739-147">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="a2739-148">**/Database**</span><span class="sxs-lookup"><span data-stu-id="a2739-148">**/Database**</span></span>|<span data-ttu-id="a2739-149">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="a2739-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a2739-150">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2739-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2739-151">参照</span><span class="sxs-lookup"><span data-stu-id="a2739-151">See Also</span></span>  
 <span data-ttu-id="a2739-152">[バインドのエクスポート](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="a2739-152">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="a2739-153">[ExportBindings コマンド](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="a2739-153">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="a2739-154">BizTalk アプリケーション、バインド、およびポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="a2739-154">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)