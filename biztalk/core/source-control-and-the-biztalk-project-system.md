---
title: ソース管理と BizTalk プロジェクト システム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft Source Code Control Interface (MSSCCI)
- projects, security
- security, projects
ms.assetid: 0f5c2f4d-5e16-4277-b750-60813a3ff964
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9b7cffc8a9572a3301a8b52ef84932910f64864
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966307"
---
# <a name="source-control-and-the-biztalk-project-system"></a><span data-ttu-id="374b5-102">ソース管理と BizTalk プロジェクト システム</span><span class="sxs-lookup"><span data-stu-id="374b5-102">Source Control and the BizTalk Project System</span></span>
<span data-ttu-id="374b5-103">ソース管理とは、ファイルのバージョンの格納や追跡を行ったり、ファイルへのアクセスを制御するメカニズムです。このメカニズムは、ソフトウェアの主要部分によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="374b5-103">Source control is a mechanism in which a central piece of software stores and tracks file versions and controls who can access the files.</span></span> <span data-ttu-id="374b5-104">ソース管理では、次の操作が行えます。</span><span class="sxs-lookup"><span data-stu-id="374b5-104">When you use source control, you can:</span></span>  
  
- <span data-ttu-id="374b5-105">重要なファイルが上書きされる可能性を軽減する。</span><span class="sxs-lookup"><span data-stu-id="374b5-105">Limit the possibility of overwriting important files.</span></span>  
  
- <span data-ttu-id="374b5-106">ファイルにバージョン番号を適用する。</span><span class="sxs-lookup"><span data-stu-id="374b5-106">Apply version numbers to your files.</span></span>  
  
- <span data-ttu-id="374b5-107">ソース管理の対象であるファイルの古いバージョンをアーカイブする。</span><span class="sxs-lookup"><span data-stu-id="374b5-107">Archive older versions of a source-controlled file.</span></span>  
  
- <span data-ttu-id="374b5-108">ファイルの編集者、編集日時および編集内容を記録する。</span><span class="sxs-lookup"><span data-stu-id="374b5-108">Keep track of who modified a file, when they modified it, and what they modified.</span></span>  
  
  <span data-ttu-id="374b5-109">Visual Studio は、MSSCCI (Microsoft Source Code Control Interface) に準拠するシステムと統合できます。</span><span class="sxs-lookup"><span data-stu-id="374b5-109">Visual Studio enables you to integrate with any Microsoft Source Code Control Interface (MSSCCI)-compliant system.</span></span> <span data-ttu-id="374b5-110">BizTalk Server、Team Foundation Server のサポートを提供およびにより、開発チームは、統合ソース管理、バグの追跡、チーム開発サポート、Microsoft Office Project Server、および自動化するためのサポートとの統合を活用するにはMSBuild を使用してビルドします。</span><span class="sxs-lookup"><span data-stu-id="374b5-110">BizTalk Server provides support for Team Foundation Server, and enables development teams to leverage the integrated source control, bug tracking, support for team development, integration with Microsoft Office Project Server, and support for automating builds by using MSBuild.</span></span> <span data-ttu-id="374b5-111">BizTalk プロジェクト システムは Microsoft Visual SourceSafe もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="374b5-111">The BizTalk project system also supports Microsoft Visual SourceSafe.</span></span>  
  
  <span data-ttu-id="374b5-112">ソース管理の詳細についてで Visual Studio 連結ヘルプ コレクション「ソース管理の基礎」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25506](http://go.microsoft.com/fwlink/?LinkId=25506)します。</span><span class="sxs-lookup"><span data-stu-id="374b5-112">For more information about source control, see "Source Control Basics" in the Visual Studio Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=25506](http://go.microsoft.com/fwlink/?LinkId=25506).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="374b5-113">参照</span><span class="sxs-lookup"><span data-stu-id="374b5-113">See Also</span></span>  
 [<span data-ttu-id="374b5-114">BizTalk プロジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="374b5-114">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)