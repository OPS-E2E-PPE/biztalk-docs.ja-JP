---
title: "ソース管理と、BizTalk プロジェクト システム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft Source Code Control Interface (MSSCCI)
- projects, security
- security, projects
ms.assetid: 0f5c2f4d-5e16-4277-b750-60813a3ff964
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34f76341752c4cfe02f0f450f215417604c4770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="source-control-and-the-biztalk-project-system"></a><span data-ttu-id="daaa0-102">ソース管理と、BizTalk プロジェクト システム</span><span class="sxs-lookup"><span data-stu-id="daaa0-102">Source Control and the BizTalk Project System</span></span>
<span data-ttu-id="daaa0-103">ソース管理とは、ファイルのバージョンの格納や追跡を行ったり、ファイルへのアクセスを制御するメカニズムです。このメカニズムは、ソフトウェアの主要部分によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="daaa0-103">Source control is a mechanism in which a central piece of software stores and tracks file versions and controls who can access the files.</span></span> <span data-ttu-id="daaa0-104">ソース管理では、次の操作が行えます。</span><span class="sxs-lookup"><span data-stu-id="daaa0-104">When you use source control, you can:</span></span>  
  
-   <span data-ttu-id="daaa0-105">重要なファイルが上書きされる可能性を軽減する。</span><span class="sxs-lookup"><span data-stu-id="daaa0-105">Limit the possibility of overwriting important files.</span></span>  
  
-   <span data-ttu-id="daaa0-106">ファイルにバージョン番号を適用する。</span><span class="sxs-lookup"><span data-stu-id="daaa0-106">Apply version numbers to your files.</span></span>  
  
-   <span data-ttu-id="daaa0-107">ソース管理の対象であるファイルの古いバージョンをアーカイブする。</span><span class="sxs-lookup"><span data-stu-id="daaa0-107">Archive older versions of a source-controlled file.</span></span>  
  
-   <span data-ttu-id="daaa0-108">ファイルの編集者、編集日時および編集内容を記録する。</span><span class="sxs-lookup"><span data-stu-id="daaa0-108">Keep track of who modified a file, when they modified it, and what they modified.</span></span>  
  
 <span data-ttu-id="daaa0-109">Visual Studio は、MSSCCI (Microsoft Source Code Control Interface) に準拠するシステムと統合できます。</span><span class="sxs-lookup"><span data-stu-id="daaa0-109">Visual Studio enables you to integrate with any Microsoft Source Code Control Interface (MSSCCI)-compliant system.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="daaa0-110"> は Team Foundation Server に対するサポートを備えているので、開発チームは、統合ソース管理、バグ追跡、チーム開発サポート、Microsoft Office Project Server との統合、および MSBuild を使用したビルド自動化サポートの各機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="daaa0-110"> provides support for Team Foundation Server, and enables development teams to leverage the integrated source control, bug tracking, support for team development, integration with Microsoft Office Project Server, and support for automating builds by using MSBuild.</span></span> <span data-ttu-id="daaa0-111">BizTalk プロジェクト システムは Microsoft Visual SourceSafe もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="daaa0-111">The BizTalk project system also supports Microsoft Visual SourceSafe.</span></span>  
  
 <span data-ttu-id="daaa0-112">ソース管理の詳細については、「ソース コントロールの基本事項」で Visual Studio 連結ヘルプ コレクションを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25506](http://go.microsoft.com/fwlink/?LinkId=25506)です。</span><span class="sxs-lookup"><span data-stu-id="daaa0-112">For more information about source control, see "Source Control Basics" in the Visual Studio Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=25506](http://go.microsoft.com/fwlink/?LinkId=25506).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaa0-113">参照</span><span class="sxs-lookup"><span data-stu-id="daaa0-113">See Also</span></span>  
 [<span data-ttu-id="daaa0-114">BizTalk プロジェクトでの作業</span><span class="sxs-lookup"><span data-stu-id="daaa0-114">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)