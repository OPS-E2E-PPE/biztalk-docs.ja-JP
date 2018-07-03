---
title: リソースを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 614cd1e2845994b5a0b009b56536f45a88f5bc2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986331"
---
# <a name="how-to-refresh-a-resource"></a><span data-ttu-id="00b3b-102">リソースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="00b3b-102">How to Refresh a Resource</span></span>
<span data-ttu-id="00b3b-103">このトピックでは、BizTalk Server 管理コンソールを使用して、リソース アイテムを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-103">This topic describes how to use the BizTalk Server Administration console to refresh a resource artifact.</span></span> <span data-ttu-id="00b3b-104">これにより、BizTalk 管理データベースのアイテム情報が更新されます。</span><span class="sxs-lookup"><span data-stu-id="00b3b-104">This updates the artifact information in the BizTalk Management database.</span></span> <span data-ttu-id="00b3b-105">これを行う別の方法は、BTSTask を使用してアプリケーションにアイテムを追加することで、 [AddResource コマンド](../core/addresource-command.md)上書きオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-105">Another way to do this is by adding the artifact to the application using the BTSTask [AddResource Command](../core/addresource-command.md) with the overwrite option.</span></span>  
  
 <span data-ttu-id="00b3b-106">リソース アイテムは、アプリケーションのリソース フォルダーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="00b3b-106">Resource artifacts are contained in an application's Resources folder.</span></span> <span data-ttu-id="00b3b-107">ソース ファイルに変更を加え、アプリケーションのファイルを更新したファイルで置き換える場合は、リソース アイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-107">You might want to refresh a resource artifact if you make changes to the source file and want to replace the file in the application with the updated file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="00b3b-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="00b3b-108">Prerequisites</span></span>  
 <span data-ttu-id="00b3b-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b3b-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="00b3b-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-refresh-a-resource-artifact"></a><span data-ttu-id="00b3b-111">リソース アイテムを更新するには</span><span class="sxs-lookup"><span data-stu-id="00b3b-111">To refresh a resource artifact</span></span>  
  
1. <span data-ttu-id="00b3b-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="00b3b-113">コンソール ツリーで、展開**BizTalk Server 管理**、更新するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the resource artifact to refresh, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="00b3b-114">をクリックして、**リソース**フォルダー、ファイルを更新するには右クリックおよびクリック**変更**します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-114">Click the **Resources** folder, right-click the file to refresh, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="00b3b-115">**リソースの変更** ダイアログ ボックスを更新するファイルを選択およびクリック**更新**します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-115">In the **Modify Resources** dialog box, select the file to refresh, and then click **Refresh**.</span></span>  
  
5. <span data-ttu-id="00b3b-116">現在のファイルを置換する更新されたファイルに参照し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="00b3b-116">Browse to the updated file with which you want to replace the current file, and then click **OK**.</span></span>  
  
    <span data-ttu-id="00b3b-117">現在のファイルが更新されたファイルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="00b3b-117">The current file is replaced with the updated file.</span></span> <span data-ttu-id="00b3b-118">加算、構成に表示される設定で、**オプション**のタブ、**リソースの変更** ダイアログ ボックスが更新されたファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="00b3b-118">In addition, the configuration, settings displayed on the **Options** tab of the **Modify Resources** dialog box are applied to the refreshed file.</span></span> <span data-ttu-id="00b3b-119">これらの設定を変更する方法についての詳細については、次のようにクリックします。**ヘルプ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="00b3b-119">For more information about changing these settings, click **Help** in the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b3b-120">参照</span><span class="sxs-lookup"><span data-stu-id="00b3b-120">See Also</span></span>  
 <span data-ttu-id="00b3b-121">[前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="00b3b-121">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 <span data-ttu-id="00b3b-122">[.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="00b3b-122">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="00b3b-123">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="00b3b-123">Managing Resources</span></span>](../core/managing-resources.md)