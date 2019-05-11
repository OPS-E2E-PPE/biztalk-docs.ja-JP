---
title: 既存のマップを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a566a76d1d42d099e1825af7d6774644bb9049d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387298"
---
# <a name="how-to-add-existing-maps"></a><span data-ttu-id="ad751-102">既存のマップを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ad751-102">How to Add Existing Maps</span></span>
<span data-ttu-id="ad751-103">既存のマップを BizTalk プロジェクトに追加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad751-103">There may be times when you want to add an existing map to a BizTalk project.</span></span> <span data-ttu-id="ad751-104">これを行うには、前に、マップの元と送信先スキーマがマップを追加する BizTalk プロジェクトに含まれることを確認する必要があります。または、対応する .NET アセンブリによって参照されています。</span><span class="sxs-lookup"><span data-stu-id="ad751-104">Before doing so, you must ensure that the source and destination schemas of the map are included in the BizTalk project to which you are adding the map; or, referenced by the corresponding .NET assembly.</span></span>  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a><span data-ttu-id="ad751-105">既存のマップを BizTalk プロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="ad751-105">To add an existing map to a BizTalk project</span></span>  
  
1. <span data-ttu-id="ad751-106">ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ad751-106">Right-click a BizTalk project in Solution Explorer, point to **Add**, and then click **Existing Item**.</span></span>  
  
2. <span data-ttu-id="ad751-107">**既存項目の追加** ダイアログ ボックスで、追加で選択しをクリックするマップを含むフォルダーを参照し**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad751-107">In the **Add Existing Item** dialog box, browse to the folder containing the map to be added, select it, and then click **Add**.</span></span>  
  
    <span data-ttu-id="ad751-108">マップは、BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="ad751-108">The map opens in BizTalk Mapper.</span></span> <span data-ttu-id="ad751-109">新しく追加したマップは、ソリューション エクスプ ローラーで現在の BizTalk プロジェクトの子としても表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad751-109">The newly added map also appears as a child of the current BizTalk project in Solution Explorer.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ad751-110">BizTalk プロジェクト フォルダー以外のフォルダーを参照した場合、プロジェクト フォルダーに追加したマップのコピーが作成されたし、このプロジェクトに追加されたマップのコピーがします。</span><span class="sxs-lookup"><span data-stu-id="ad751-110">If you browsed to a folder other than the BizTalk project folder, a copy of the map you added was created in the project folder, and it was this copy of the map that was added to the project.</span></span> <span data-ttu-id="ad751-111">その後、マップに変更は、他のフォルダー内の元のマップが、このコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ad751-111">Subsequent changes to the map are made to this copy, not to the original map in the other folder.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="ad751-112">BizTalk マップは、Microsoft 内でホストされている BizTalk マッパーによってのみ開くこと[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。</span><span class="sxs-lookup"><span data-stu-id="ad751-112">BizTalk maps can only be opened by BizTalk Mapper, which is hosted within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="ad751-113">Windows エクスプ ローラーの新しいインスタンスのマップをダブルクリック[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、開く、マップが BizTalk マッパーで表示されます、対応するスキーマが正しく読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="ad751-113">If you double-click a map in Windows Explorer, a new instance of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will be opened, and then the map will be opened by BizTalk Mapper, provided the corresponding schemas are loaded properly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ad751-114">既存のマップにカスタム functoid が含まれている場合、"%BTSINSTALLPATH%\Developer tools \mapper Extensions"フォルダーに対応する Dll をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad751-114">If the existing map contains custom functoids, then the corresponding DLLs must be copied to the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span> <span data-ttu-id="ad751-115">それ以外の場合、マップは読み込まれず、カスタム functoid の読み込みに失敗したため、エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="ad751-115">Else, the map will not load and throws an error because of failure to load custom functoids.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad751-116">参照</span><span class="sxs-lookup"><span data-stu-id="ad751-116">See Also</span></span>  
 <span data-ttu-id="ad751-117">[プロジェクト内のマップを管理します。](../core/managing-maps-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="ad751-117">[Managing Maps Within Projects](../core/managing-maps-within-projects.md) </span></span>  
 [<span data-ttu-id="ad751-118">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="ad751-118">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)