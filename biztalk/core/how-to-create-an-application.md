---
title: アプリケーションを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b81a90c4e013d9eb8d882f2d9901e70920d0c46a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983059"
---
# <a name="how-to-create-an-application"></a><span data-ttu-id="b8e56-102">アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b8e56-102">How to Create an Application</span></span>
<span data-ttu-id="b8e56-103">新しい BizTalk アプリケーションを作成するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-103">There are three ways to create a new BizTalk application:</span></span>  
  
- <span data-ttu-id="b8e56-104">BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-104">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="b8e56-105">この手順については、このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-105">You can find the procedures for doing this later in this topic.</span></span>  
  
- <span data-ttu-id="b8e56-106">他のアプリケーションからエクスポートした .msi ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b8e56-106">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="b8e56-107">アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8e56-107">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="b8e56-108">詳細については、[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e56-108">For more information, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="b8e56-109">Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-109">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="b8e56-110">Visual Studio で指定されたアプリケーションが現在の BizTalk グループに存在しない場合、そのアプリケーションは自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8e56-110">If the application specified in Visual Studio does not already exist in the current BizTalk group, it is automatically created.</span></span> <span data-ttu-id="b8e56-111">詳細については、[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e56-111">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="b8e56-112">新しいアプリケーションを作成する前に、次のオプションの構成方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="b8e56-112">Before creating a new application, you might want to decide how to configure the following options:</span></span>  
  
- <span data-ttu-id="b8e56-113">**新しいアプリケーションの名前を何か。**</span><span class="sxs-lookup"><span data-stu-id="b8e56-113">**What to name the new application.**</span></span> <span data-ttu-id="b8e56-114">BizTalk グループの各アプリケーションには、一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-114">Each application in the BizTalk group must have a unique name.</span></span>  
  
- <span data-ttu-id="b8e56-115">**かどうかは、他のアプリケーションへの参照を追加する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="b8e56-115">**Whether you need to add any references to other applications.**</span></span> <span data-ttu-id="b8e56-116">このアプリケーションから、このアプリケーションで再利用するアイテムを含むアプリケーションへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-116">You must add a reference from this application to any applications containing artifacts that you want to reuse in this application.</span></span> <span data-ttu-id="b8e56-117">これにより 2 つのアプリケーションの間の依存関係が作成され、これらのアプリケーションの展開方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-117">This creates a dependency between the applications, which affects the way that you must deploy them.</span></span> <span data-ttu-id="b8e56-118">背景情報は、[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)と[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e56-118">For background information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md) and [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
- <span data-ttu-id="b8e56-119">**かどうかは、1 つ以上のアプリケーションを作成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="b8e56-119">**Whether you need to create more than one application.**</span></span> <span data-ttu-id="b8e56-120">アイテムによっては、独立したアプリケーションに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-120">You may need to deploy some artifacts into separate applications.</span></span> <span data-ttu-id="b8e56-121">たとえば、共有アイテムは、独自の独立したアプリケーションに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-121">For example, shared artifacts should be deployed into their own, separate application.</span></span> <span data-ttu-id="b8e56-122">詳細については、[BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e56-122">For more information, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="b8e56-123">アプリケーションを作成した後にアイテムを追加および他のトピックでは、このセクションで説明されているように他の変更を行う ([を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md))。</span><span class="sxs-lookup"><span data-stu-id="b8e56-123">Once you have created an application, you can add artifacts to it and make other modifications, as described in the other topics in this section ([Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md)).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b8e56-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="b8e56-124">Prerequisites</span></span>  
 <span data-ttu-id="b8e56-125">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-125">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="b8e56-126">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-126">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-create-a-biztalk-application"></a><span data-ttu-id="b8e56-127">BizTalk アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="b8e56-127">To create a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="b8e56-128">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="b8e56-128">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="b8e56-129">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-129">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b8e56-130">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、新しいアプリケーションを作成する BizTalk グループを右クリックして**新規**、 をクリックし、**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-130">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the BizTalk group in which you want to create the new application, point to **New**, and then click **Application**.</span></span>  
  
3. <span data-ttu-id="b8e56-131">**名前**アプリケーションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-131">In **Name**, type the name of the application.</span></span> <span data-ttu-id="b8e56-132">名前は、BizTalk グループ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-132">The name must be unique in the BizTalk group.</span></span>  
  
4. <span data-ttu-id="b8e56-133">この BizTalk グループの既定のアプリケーションを作成する場合は、選択、 **、既定のアプリケーションをこのように**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="b8e56-133">If you want to make this the default application for the BizTalk group, select the **Make this the default application** check box.</span></span>  
  
5. <span data-ttu-id="b8e56-134">**説明**アプリケーションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-134">In **Description**, type a description for the application.</span></span>  
  
6. <span data-ttu-id="b8e56-135">このアプリケーションは、別のアプリケーションからアイテムを再利用は、クリックして**参照**残りの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b8e56-135">If this application will reuse artifacts from another application, click **References** and follow the remaining steps.</span></span> <span data-ttu-id="b8e56-136">それ以外の場合、をクリックして**OK**さらに手順を実行しません。</span><span class="sxs-lookup"><span data-stu-id="b8e56-136">Otherwise, click **OK** and take no further steps.</span></span>  
  
7. <span data-ttu-id="b8e56-137">をクリックして**追加**、クリックしてこのアプリケーションで再利用するアイテムを含むアプリケーションを選択します**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-137">Click **Add**, select the application that contains the artifacts you want to reuse in this application, and then click **OK**.</span></span> <span data-ttu-id="b8e56-138">追加の参照を追加するアプリケーションには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-138">Repeat this step for any additional applications for which you want to add references.</span></span>  
  
8. <span data-ttu-id="b8e56-139">一覧からアプリケーションを削除する場合は、アプリケーションを選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-139">If you want to remove an application from the list, select the application and click **Remove**.</span></span>  
  
9. <span data-ttu-id="b8e56-140">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8e56-140">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="b8e56-141">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="b8e56-141">Using the command line</span></span>  
  
1. <span data-ttu-id="b8e56-142">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="b8e56-142">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b8e56-143">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-143">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="b8e56-144">**BTSTask AddApp/applicationname は:** *値\*\*\*[/既定値]*\* [**/Description:**<em>値</em>] [**/サーバー:**<em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="b8e56-144">**BTSTask AddApp /ApplicationName:** *value* [**/Default**] [**/Description:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="b8e56-145">例:</span><span class="sxs-lookup"><span data-stu-id="b8e56-145">Example:</span></span>  
  
    <span data-ttu-id="b8e56-146">**BTSTask AddApp applicationname: myapplication/Description:"私のお気に入り application"/Server:MySQLServer/Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="b8e56-146">**BTSTask AddApp /ApplicationName:MyApplication /Description:"My favorite application" /Server:MySQLServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="b8e56-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8e56-147">Parameter</span></span>|<span data-ttu-id="b8e56-148">値</span><span class="sxs-lookup"><span data-stu-id="b8e56-148">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="b8e56-149">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="b8e56-149">**/ApplicationName**</span></span>|<span data-ttu-id="b8e56-150">作成されるアプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="b8e56-150">Name of the application to be created.</span></span> <span data-ttu-id="b8e56-151">空白を含む名前は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-151">Names containing spaces must be enclosed in double quotation marks (").</span></span>|  
   |<span data-ttu-id="b8e56-152">**/既定**</span><span class="sxs-lookup"><span data-stu-id="b8e56-152">**/Default**</span></span>|<span data-ttu-id="b8e56-153">指定した場合、BizTalk グループの既定のアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-153">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
   |<span data-ttu-id="b8e56-154">**/説明**</span><span class="sxs-lookup"><span data-stu-id="b8e56-154">**/Description**</span></span>|<span data-ttu-id="b8e56-155">アプリケーションの説明。</span><span class="sxs-lookup"><span data-stu-id="b8e56-155">Description of the application.</span></span> <span data-ttu-id="b8e56-156">空白を含む説明は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e56-156">Descriptions containing spaces must be enclosed in double quotation marks (").</span></span>|  
   |<span data-ttu-id="b8e56-157">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="b8e56-157">**/Server**</span></span>|<span data-ttu-id="b8e56-158">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="b8e56-158">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="b8e56-159">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="b8e56-159">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="b8e56-160">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="b8e56-160">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="b8e56-161">例 :</span><span class="sxs-lookup"><span data-stu-id="b8e56-161">Examples:</span></span><br /><br /> <span data-ttu-id="b8e56-162">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="b8e56-162">Server=MyServer</span></span><br /><br /> <span data-ttu-id="b8e56-163">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="b8e56-163">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="b8e56-164">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8e56-164">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="b8e56-165">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="b8e56-165">**/Database**</span></span>|<span data-ttu-id="b8e56-166">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b8e56-166">Name of the BizTalk Management database.</span></span> <span data-ttu-id="b8e56-167">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8e56-167">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8e56-168">参照</span><span class="sxs-lookup"><span data-stu-id="b8e56-168">See Also</span></span>  
 <span data-ttu-id="b8e56-169">[作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b8e56-169">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="b8e56-170">AddApp コマンド</span><span class="sxs-lookup"><span data-stu-id="b8e56-170">AddApp Command</span></span>](../core/addapp-command.md)