---
title: BizTalk グループにバインドをインポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64bac6c64a9aadc772bfe8445b23f87b469471d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970136"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="23220-102">BizTalk グループにバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="23220-102">How to Import Bindings into a BizTalk Group</span></span>
<span data-ttu-id="23220-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、.xml ファイルからBizTalk グループにバインドをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23220-103">This topic describes how to use the BizTalk Server Administration console or the command line to import bindings into a BizTalk group from an .xml file.</span></span> <span data-ttu-id="23220-104">BizTalk グループからバインドをインポートできる .xml ファイルにエクスポートする方法については、次を参照してください。 [BizTalk グループのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="23220-104">For instructions on exporting the bindings from a BizTalk group into an .xml file that you can import, see [How to Export Bindings for a BizTalk Group](../core/how-to-export-bindings-for-a-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="23220-105">」の説明に従って、BizTalk アプリケーションにバインドにインポートすることもできます[BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="23220-105">You can also import bindings into a BizTalk application, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="23220-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="23220-106">Prerequisites</span></span>  
 <span data-ttu-id="23220-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23220-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="23220-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="23220-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a><span data-ttu-id="23220-109">BizTalk グループにバインドをインポートするには</span><span class="sxs-lookup"><span data-stu-id="23220-109">To import bindings into a BizTalk group</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="23220-110">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="23220-110">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="23220-111">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="23220-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="23220-112">コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループを展開し、右クリックし、**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="23220-112">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and then right-click **Applications**.</span></span>  
  
3.  <span data-ttu-id="23220-113">をポイント**インポート**、クリックして**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="23220-113">Point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="23220-114">バインド ファイルをクリックし、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="23220-114">Click the binding file and click **Open**.</span></span>  
  
     <span data-ttu-id="23220-115">バインド ファイルのアイテムがグループに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="23220-115">The artifacts in the binding file are written to the group.</span></span> <span data-ttu-id="23220-116">適切なフォルダーに表示される、\<すべての成果物\>ノード。</span><span class="sxs-lookup"><span data-stu-id="23220-116">They display in appropriate folders of the \<All Artifacts\> node.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="23220-117">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="23220-117">Using the command line</span></span>  
  
1.  <span data-ttu-id="23220-118">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="23220-118">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="23220-119">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="23220-119">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="23220-120">**BTSTask ImportBindings/Source:** *値* **/grouplevel は**[**/Server:***値*] [**/データベース:***値*]</span><span class="sxs-lookup"><span data-stu-id="23220-120">**BTSTask ImportBindings /Source:** *value* **/GroupLevel** [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="23220-121">たとえば、次のコマンドは、SQL Server インスタンス (MyServer) 上で実行されている BizTalk 管理データベースで定義されたグループにバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="23220-121">For example, the following command imports bindings into the group defined in the BizTalk Management database running on a SQL Server instance named MyServer.</span></span>  
  
     <span data-ttu-id="23220-122">**BTSTask ImportBindings GroupLevel/Server:MyServer/Database:BiztalkMgmtDb/Source:C:\Bindings\Binding1.xml**</span><span class="sxs-lookup"><span data-stu-id="23220-122">**BTSTask ImportBindings /GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**</span></span>  
  
    |<span data-ttu-id="23220-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23220-123">Parameter</span></span>|<span data-ttu-id="23220-124">値</span><span class="sxs-lookup"><span data-stu-id="23220-124">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="23220-125">**/ソース**</span><span class="sxs-lookup"><span data-stu-id="23220-125">**/Source**</span></span>|<span data-ttu-id="23220-126">インポートするバインド ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="23220-126">Full path of the binding file to import, including the file name.</span></span> <span data-ttu-id="23220-127">パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="23220-127">Paths that include spaces must be enclosed in quotation marks (").</span></span>|  
    |<span data-ttu-id="23220-128">**/GroupLevel**</span><span class="sxs-lookup"><span data-stu-id="23220-128">**/GroupLevel**</span></span>|<span data-ttu-id="23220-129">バインド ファイルを現在のグループにインポートするためのオプション。</span><span class="sxs-lookup"><span data-stu-id="23220-129">Option to import the binding file into the current group.</span></span>|  
    |<span data-ttu-id="23220-130">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="23220-130">**/Server**</span></span>|<span data-ttu-id="23220-131">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="23220-131">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="23220-132">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="23220-132">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="23220-133">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="23220-133">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="23220-134">例 :</span><span class="sxs-lookup"><span data-stu-id="23220-134">Examples:</span></span><br /><br /> <span data-ttu-id="23220-135">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="23220-135">Server=MyServer</span></span><br /><br /> <span data-ttu-id="23220-136">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="23220-136">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="23220-137">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="23220-137">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="23220-138">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="23220-138">**/Database**</span></span>|<span data-ttu-id="23220-139">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="23220-139">Name of the BizTalk Management database.</span></span> <span data-ttu-id="23220-140">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="23220-140">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23220-141">参照</span><span class="sxs-lookup"><span data-stu-id="23220-141">See Also</span></span>  
 <span data-ttu-id="23220-142">[BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="23220-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="23220-143">ImportBindings コマンド</span><span class="sxs-lookup"><span data-stu-id="23220-143">ImportBindings Command</span></span>](../core/importbindings-command.md)