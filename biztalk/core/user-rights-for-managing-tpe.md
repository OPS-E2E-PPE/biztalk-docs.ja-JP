---
title: TPE を管理するためのユーザー権利 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3319a807b1357201dade0c53d04c26146c2b1e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286930"
---
# <a name="user-rights-for-managing-tpe"></a><span data-ttu-id="6b745-102">TPE を管理するためのユーザー権利</span><span class="sxs-lookup"><span data-stu-id="6b745-102">User Rights for Managing TPE</span></span>
<span data-ttu-id="6b745-103">ソリューション開発者、システム管理者、または IT 担当者や運用担当者が、追跡プロファイルを取得したり、アセンブリに関連付けられたデータベースに追跡プロファイルを展開するには、管理権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b745-103">Solution developers, system administrators, or IT/Operations personnel must have administrative rights to retrieve or deploy the tracking profile into a database associated with an assembly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b745-104">追跡プロファイル エディター (TPE) を使用して、ユーザー ロールを定義したり、ユーザー権限を許可または拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b745-104">You cannot define user roles or grant or deny user permissions using Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="6b745-105">Microsoft SQL Server では、これらのユーザー ロールおよび関連付けられた権限の定義のみを行えます。</span><span class="sxs-lookup"><span data-stu-id="6b745-105">You can only define these user roles and associated permissions in Microsoft SQL Server.</span></span>  
  
 <span data-ttu-id="6b745-106">TPE では、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b745-106">With TPE, administrators can:</span></span>  
  
-   <span data-ttu-id="6b745-107">BizTalk 管理データベースから、1 つ以上のアセンブリに関連付けられたアクティブな追跡プロファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b745-107">Retrieve an active tracking profile associated with one or more assemblies from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="6b745-108">追跡プロファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b745-108">Modify the tracking profile</span></span>  
  
-   <span data-ttu-id="6b745-109">新しい追跡プロファイルまたは変更した追跡プロファイルを、BizTalk 管理データベースに適用します。</span><span class="sxs-lookup"><span data-stu-id="6b745-109">Apply a new or modified tracking profile into the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="6b745-110">保存済みの追跡プロファイル ファイル (.btt) を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b745-110">Modify saved tracking profile files (.btt)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b745-111">追跡プロファイル ファイルは、プロファイルの内容が示される最終的な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="6b745-111">Tracking profile files are not the final authority on the contents of a profile.</span></span> <span data-ttu-id="6b745-112">TPE では、主にプロファイルの内容を BizTalk Server から抽出して BAM データベースに公開しますが、プロファイルをファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="6b745-112">TPE can save a profile to a file, although it primarily pulls from and publishes the profile contents to the BizTalk Server and BAM databases.</span></span> <span data-ttu-id="6b745-113">追跡プロファイル ファイルは、ファイルの内容がデータベースに格納されている情報と一致する限り、保存されているプロファイルを編集または更新するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b745-113">Tracking profile files can still be used to edit or update the stored profile as long as the file contents match the information stored in the databases.</span></span> <span data-ttu-id="6b745-114">さらに、追跡プロファイル ファイルは、BizTalk Server アプリケーション パッケージ内にパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="6b745-114">In addition, tracking profile files can be packaged within a BizTalk Server application package.</span></span> <span data-ttu-id="6b745-115">追跡プロファイル ファイルを含むアプリケーション パッケージは、MSI パッケージが特定の BizTalk Server インストールにインポートされると、自動的に BTTDeploy.exe を呼び出して追跡プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="6b745-115">Application packages that include tracking profile files automatically invoke BTTDeploy.exe to apply the tracking profile when the MSI package is imported to a given BizTalk Server installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b745-116">TPE ワークフローで開発タスクと展開タスクが分離されていると想定した場合、通常、展開の担当者には、.btt ファイルおよび関連付けられたアセンブリ ファイルへの読み取り専用アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b745-116">In the TPE workflow, assuming the development and deployment tasks are separated, as is typically the case, the person responsible for deployment should have read-only access to the .btt file and the associated assembly file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b745-117">参照</span><span class="sxs-lookup"><span data-stu-id="6b745-117">See Also</span></span>  
 <span data-ttu-id="6b745-118">[BAM のワークフロー](../core/bam-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="6b745-118">[BAM Workflow](../core/bam-workflow.md) </span></span>  
 [<span data-ttu-id="6b745-119">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="6b745-119">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)