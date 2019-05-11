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
ms.openlocfilehash: f8515bcd3197c1532906cf90863e1e03faa9aabe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384414"
---
# <a name="how-to-refresh-a-resource"></a><span data-ttu-id="cb6f4-102">リソースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="cb6f4-102">How to Refresh a Resource</span></span>
<span data-ttu-id="cb6f4-103">このトピックでは、BizTalk Server 管理コンソールを使用して、リソース アイテムを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-103">This topic describes how to use the BizTalk Server Administration console to refresh a resource artifact.</span></span> <span data-ttu-id="cb6f4-104">これは、BizTalk 管理データベースのアイテム情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-104">This updates the artifact information in the BizTalk Management database.</span></span> <span data-ttu-id="cb6f4-105">これを行う別の方法は、BTSTask を使用してアプリケーションにアイテムを追加することで、 [AddResource コマンド](../core/addresource-command.md)上書きオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-105">Another way to do this is by adding the artifact to the application using the BTSTask [AddResource Command](../core/addresource-command.md) with the overwrite option.</span></span>  
  
 <span data-ttu-id="cb6f4-106">リソース アイテムは、アプリケーションのリソース フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-106">Resource artifacts are contained in an application's Resources folder.</span></span> <span data-ttu-id="cb6f4-107">ソース ファイルを変更し、更新されたファイルで、アプリケーションでファイルを置き換える場合は、リソース アイテムを更新する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-107">You might want to refresh a resource artifact if you make changes to the source file and want to replace the file in the application with the updated file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb6f4-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb6f4-108">Prerequisites</span></span>  
 <span data-ttu-id="cb6f4-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="cb6f4-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-refresh-a-resource-artifact"></a><span data-ttu-id="cb6f4-111">リソース アイテムを更新するには</span><span class="sxs-lookup"><span data-stu-id="cb6f4-111">To refresh a resource artifact</span></span>  
  
1. <span data-ttu-id="cb6f4-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cb6f4-113">コンソール ツリーで、展開**BizTalk Server 管理**、更新するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the resource artifact to refresh, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="cb6f4-114">をクリックして、**リソース**フォルダー、ファイルを更新するには右クリックおよびクリック**変更**します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-114">Click the **Resources** folder, right-click the file to refresh, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="cb6f4-115">**リソースの変更** ダイアログ ボックスを更新するファイルを選択およびクリック**更新**します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-115">In the **Modify Resources** dialog box, select the file to refresh, and then click **Refresh**.</span></span>  
  
5. <span data-ttu-id="cb6f4-116">現在のファイルを置換する更新されたファイルに参照し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-116">Browse to the updated file with which you want to replace the current file, and then click **OK**.</span></span>  
  
    <span data-ttu-id="cb6f4-117">現在のファイルが更新されたファイルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-117">The current file is replaced with the updated file.</span></span> <span data-ttu-id="cb6f4-118">加算、構成に表示される設定で、**オプション**のタブ、**リソースの変更** ダイアログ ボックスが更新されたファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-118">In addition, the configuration, settings displayed on the **Options** tab of the **Modify Resources** dialog box are applied to the refreshed file.</span></span> <span data-ttu-id="cb6f4-119">これらの設定を変更する方法についての詳細については、次のようにクリックします。**ヘルプ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cb6f4-119">For more information about changing these settings, click **Help** in the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6f4-120">参照</span><span class="sxs-lookup"><span data-stu-id="cb6f4-120">See Also</span></span>  
 <span data-ttu-id="cb6f4-121">[前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="cb6f4-121">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 <span data-ttu-id="cb6f4-122">[.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="cb6f4-122">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="cb6f4-123">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="cb6f4-123">Managing Resources</span></span>](../core/managing-resources.md)