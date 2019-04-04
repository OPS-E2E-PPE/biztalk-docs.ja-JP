---
title: マップの管理 |Microsoft Docs
description: リンクを表示するマップを削除するなど、BizTalk Server のマップを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6957a4f3d73c5f59df5cd36f70a7ed34631fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019832"
---
# <a name="manage-maps"></a><span data-ttu-id="15e7a-103">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-103">Manage Maps</span></span>

## <a name="overview"></a><span data-ttu-id="15e7a-104">概要</span><span class="sxs-lookup"><span data-stu-id="15e7a-104">Overview</span></span>
<span data-ttu-id="15e7a-105">ここでは、BizTalk Server 管理コンソールを使用してマップを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-105">This section provides instructions on managing maps by using the BizTalk Server Administration console.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="15e7a-106">は、マップを使用して、あるスキーマのレコードとフィールドを別のスキーマのレコードとフィールドに変換します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-106">uses maps to translate the records and fields in one schema to the records and fields in another schema.</span></span> <span data-ttu-id="15e7a-107">マップは、オーケストレーション、送信ポート、および受信ポートで使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="15e7a-107">Maps may be used by orchestrations, send ports, and receive ports.</span></span>  

## <a name="add-maps-to-an-application"></a><span data-ttu-id="15e7a-108">マップをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-108">Add maps to an application</span></span>  
 <span data-ttu-id="15e7a-109">マップは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="15e7a-109">Maps are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="15e7a-110">マップを単独でアプリケーションに追加することはできません。マップは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="15e7a-110">You cannot add a map to an application individually; a map is added to an application as follows:</span></span>  
  
- <span data-ttu-id="15e7a-111">」の説明に従って、アプリケーションに、マップを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-111">When you add a BizTalk assembly containing a map to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="15e7a-112">」の説明に従って、マップを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-112">When you import an .msi file into an application that includes a BizTalk assembly containing a map, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="15e7a-113">開発者が展開したときに、アプリケーションからマップを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="15e7a-113">When a developer deploys into an application an assembly containing a map from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="15e7a-114">マップの背景については、[マップ](../core/maps.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e7a-114">For background information about maps, see [Maps](../core/maps.md).</span></span> <span data-ttu-id="15e7a-115">マップを作成する方法の詳細については、[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e7a-115">For information about creating maps, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15e7a-116">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="15e7a-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="15e7a-117">WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e7a-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="15e7a-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="15e7a-118">Next steps</span></span> 
  
-   [<span data-ttu-id="15e7a-119">アプリケーションのマップを表示する</span><span class="sxs-lookup"><span data-stu-id="15e7a-119">View the Maps for an Application</span></span>](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [<span data-ttu-id="15e7a-120">マップをアプリケーションから削除する</span><span class="sxs-lookup"><span data-stu-id="15e7a-120">Remove a Map from an Application</span></span>](../core/how-to-remove-a-map-from-an-application.md)