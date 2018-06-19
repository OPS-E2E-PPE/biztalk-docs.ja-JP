---
title: BizTalk グループのバインドをエクスポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df08f99a9e37bf1a4d4a794c17d483fdc381f463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253986"
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="a8608-102">BizTalk グループのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="a8608-102">How to Export Bindings for a BizTalk Group</span></span>
<span data-ttu-id="a8608-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルに BizTalk グループのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8608-103">This topic describes how to use the BizTalk Server Administration console or the command line to export the bindings for a BizTalk group to an .xml file.</span></span> <span data-ttu-id="a8608-104">」の説明に従って、BizTalk グループまたはアプリケーションにこれらのバインドにインポートすること、ことができます[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)と[BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="a8608-104">You can then import these bindings into a BizTalk group or application, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md) and [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span> <span data-ttu-id="a8608-105">バインド ファイルの使用の詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="a8608-105">For more information about using binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8608-106">グループのバインドをエクスポートすると、オプションが指定されているかどうかに関係なく、常にグローバル パーティ情報がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a8608-106">Exporting bindings for a group always exports global party information, whether this option is specified or not.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8608-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a8608-107">Prerequisites</span></span>  
 <span data-ttu-id="a8608-108">このトピックの手順を実行するには、BizTalk Server 管理者または BizTalk Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8608-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="a8608-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="a8608-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a><span data-ttu-id="a8608-110">BizTalk グループのバインドをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a8608-110">To export bindings for a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a8608-111">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="a8608-111">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="a8608-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a8608-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a8608-113">コンソール ツリーで [[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を BizTalk グループを展開しを右クリックして**アプリケーション**、] をポイント**エクスポート**、順にクリック**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="a8608-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **Applications**, point to **Export**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="a8608-114">バインドのエクスポート ページで**ファイルへのエクスポート**バインドのエクスポート先 .xml ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8608-114">On the Export Bindings page, in **Export to file**, type the absolute path of the .xml file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="a8608-115">例: C:\Bindings\Group1Bindings_Staging1.xml</span><span class="sxs-lookup"><span data-stu-id="a8608-115">Example: C:\Bindings\Group1Bindings_Staging1.xml</span></span>  
  
4.  <span data-ttu-id="a8608-116">いることを確認 **、現在のグループからすべてのバインドをエクスポート**を選択して、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a8608-116">Ensure that **Export all bindings from the current group** is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a8608-117">指定した場所の .xml ファイルに、バインドがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a8608-117">The bindings are exported to an .xml file in the location that you specified.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a8608-118">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="a8608-118">Using the command line</span></span>  
  
1.  <span data-ttu-id="a8608-119">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="a8608-119">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a8608-120">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8608-120">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="a8608-121">**BTSTask ExportBindings/Destination:** *値* **/grouplevel は**[**/GlobalParties**] [**/Server:** *値*] [**/database:***値*]</span><span class="sxs-lookup"><span data-stu-id="a8608-121">**BTSTask ExportBindings /Destination:** *value* **/GroupLevel** [**/GlobalParties**] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="a8608-122">例:</span><span class="sxs-lookup"><span data-stu-id="a8608-122">Example:</span></span>  
  
     <span data-ttu-id="a8608-123">**BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"GroupLevel/Server:MyDatabaseServer/Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="a8608-123">**BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="a8608-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8608-124">Parameter</span></span>|<span data-ttu-id="a8608-125">値</span><span class="sxs-lookup"><span data-stu-id="a8608-125">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="a8608-126">**/対象**</span><span class="sxs-lookup"><span data-stu-id="a8608-126">**/Destination**</span></span>|<span data-ttu-id="a8608-127">作成するバインド ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="a8608-127">Full path of the binding file to create, including the file name.</span></span> <span data-ttu-id="a8608-128">同じパスの既存のバインド ファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a8608-128">If a binding file having the same path already exists, it is overwritten.</span></span> <span data-ttu-id="a8608-129">パスにスペースがある場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8608-129">If there are spaces in the path, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="a8608-130">**/GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="a8608-130">**/GroupLevel**</span></span>|<span data-ttu-id="a8608-131">指定した場合、現在の BizTalk グループのすべてのバインドがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a8608-131">When specified, all bindings in the current BizTalk group are exported.</span></span>|  
    |<span data-ttu-id="a8608-132">**/GlobalParties**</span><span class="sxs-lookup"><span data-stu-id="a8608-132">**/GlobalParties**</span></span>|<span data-ttu-id="a8608-133">指定した場合、グループのグローバル パーティ情報をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a8608-133">When specified, exports global party information for the group.</span></span>|  
    |<span data-ttu-id="a8608-134">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="a8608-134">**/Server**</span></span>|<span data-ttu-id="a8608-135">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a8608-135">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="a8608-136">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a8608-136">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="a8608-137">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a8608-137">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="a8608-138">例 :</span><span class="sxs-lookup"><span data-stu-id="a8608-138">Examples:</span></span><br /><br /> <span data-ttu-id="a8608-139">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="a8608-139">Server=MyServer</span></span><br /><br /> <span data-ttu-id="a8608-140">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="a8608-140">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="a8608-141">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8608-141">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="a8608-142">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="a8608-142">**/Database**</span></span>|<span data-ttu-id="a8608-143">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="a8608-143">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a8608-144">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8608-144">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8608-145">参照</span><span class="sxs-lookup"><span data-stu-id="a8608-145">See Also</span></span>  
 <span data-ttu-id="a8608-146">[バインドをエクスポートします。](../core/exporting-bindings6.md) </span><span class="sxs-lookup"><span data-stu-id="a8608-146">[Exporting Bindings](../core/exporting-bindings6.md) </span></span>  
 <span data-ttu-id="a8608-147">[ExportBindings コマンド](../core/exportbindings-command.md) </span><span class="sxs-lookup"><span data-stu-id="a8608-147">[ExportBindings Command](../core/exportbindings-command.md) </span></span>  
 [<span data-ttu-id="a8608-148">BizTalk アプリケーション、バインド、およびポリシーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a8608-148">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)