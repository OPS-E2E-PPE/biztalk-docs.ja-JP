---
title: BizTalk アプリケーションにバインドをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30cd7c587f09911b1ce3e16c21aae265a0a94ea8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385003"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="a2cb9-102">BizTalk アプリケーションにバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="a2cb9-102">How to Import Bindings into a BizTalk Application</span></span>
<span data-ttu-id="a2cb9-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルから BizTalk アプリケーションにバインドをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk application from an .xml file.</span></span> <span data-ttu-id="a2cb9-104">」の説明に従って、BizTalk グループにバインドにインポートすることもできます[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-104">You can also import bindings into a BizTalk group, as described in [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="a2cb9-105">バインドは、アセンブリ、アプリケーション、グループからエクスポートしたものをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-105">You can import bindings that have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="a2cb9-106">グループのバインドをインポートする場合、同じ名前を持つアプリケーションのバインドだけが、バインドのインポート先のアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-106">If you import group bindings, only the bindings for an application having the same name are applied to the application into which you import the bindings.</span></span> <span data-ttu-id="a2cb9-107">異なる名前のアプリケーションからバインドをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-107">You can also import bindings from an application that has a different name.</span></span> <span data-ttu-id="a2cb9-108">バインドのエクスポート手順については、次を参照してください。[バインドのエクスポート](../core/exporting-bindings6.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-108">For instructions on exporting bindings, see [Exporting Bindings](../core/exporting-bindings6.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2cb9-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a2cb9-109">Prerequisites</span></span>  
 <span data-ttu-id="a2cb9-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a2cb9-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a><span data-ttu-id="a2cb9-112">BizTalk アプリケーションにバインドをインポートするには</span><span class="sxs-lookup"><span data-stu-id="a2cb9-112">To import bindings into a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a2cb9-113">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="a2cb9-113">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="a2cb9-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a2cb9-115">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ]、[アプリケーション] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand Applications.</span></span>  
  
3. <span data-ttu-id="a2cb9-116">ポイントして、バインドをインポートするアプリケーションを右クリックして**インポート**、 をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-116">Right-click the application into which you want to import bindings, point to **Import**, and then click **Bindings**.</span></span>  
  
4. <span data-ttu-id="a2cb9-117">バインド ファイルをクリックし、をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-117">Click the binding file and click **Open**.</span></span>  
  
    <span data-ttu-id="a2cb9-118">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-118">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="a2cb9-119">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-119">They display in appropriate folders of the application.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a2cb9-120">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="a2cb9-120">Using the command line</span></span>  
  
1. <span data-ttu-id="a2cb9-121">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-121">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a2cb9-122">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-122">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="a2cb9-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="a2cb9-123">**BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="a2cb9-124">たとえば、次のコマンドは、既定の BizTalk グループの MyApplication というアプリケーションにバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-124">For example, the following command imports bindings into the application named MyApplication in the default BizTalk group.</span></span>  
  
    <span data-ttu-id="a2cb9-125">**BTSTask ImportBindings applicationname: myapplication** /**Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="a2cb9-125">**BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**</span></span>  
  
   |<span data-ttu-id="a2cb9-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2cb9-126">Parameter</span></span>|<span data-ttu-id="a2cb9-127">値</span><span class="sxs-lookup"><span data-stu-id="a2cb9-127">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="a2cb9-128">**/ソース**</span><span class="sxs-lookup"><span data-stu-id="a2cb9-128">**/Source**</span></span>|<span data-ttu-id="a2cb9-129">インポートするバインド ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-129">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="a2cb9-130">パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-130">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="a2cb9-131">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="a2cb9-131">**/ApplicationName**</span></span>|<span data-ttu-id="a2cb9-132">バインドをインポートする BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-132">Name of the BizTalk application into which the bindings are to be imported.</span></span> <span data-ttu-id="a2cb9-133">アプリケーションが存在している必要があります。アプリケーションが存在しない場合、インポート操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-133">The application must exist or the import operation will fail.</span></span> <span data-ttu-id="a2cb9-134">このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-134">If this parameter is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="a2cb9-135">アプリケーション名にスペースが含まれる場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-135">Application names that include spaces must be enclosed in quotation marks (").</span></span>|  
   |<span data-ttu-id="a2cb9-136">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="a2cb9-136">**/Server**</span></span>|<span data-ttu-id="a2cb9-137">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-137">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="a2cb9-138">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-138">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="a2cb9-139">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-139">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="a2cb9-140">例 :</span><span class="sxs-lookup"><span data-stu-id="a2cb9-140">Examples:</span></span><br /><br /> <span data-ttu-id="a2cb9-141">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="a2cb9-141">Server=MyServer</span></span><br /><br /> <span data-ttu-id="a2cb9-142">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="a2cb9-142">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="a2cb9-143">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-143">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="a2cb9-144">**/Database**</span><span class="sxs-lookup"><span data-stu-id="a2cb9-144">**/Database**</span></span>|<span data-ttu-id="a2cb9-145">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-145">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a2cb9-146">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2cb9-146">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2cb9-147">参照</span><span class="sxs-lookup"><span data-stu-id="a2cb9-147">See Also</span></span>  
 <span data-ttu-id="a2cb9-148">[BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="a2cb9-148">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="a2cb9-149">ImportBindings コマンド</span><span class="sxs-lookup"><span data-stu-id="a2cb9-149">ImportBindings Command</span></span>](../core/importbindings-command.md)