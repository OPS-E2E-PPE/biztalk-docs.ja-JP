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
ms.openlocfilehash: 415a5112c5cca457f7cbbe229ce073219de95631
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970145"
---
# <a name="how-to-add-existing-maps"></a><span data-ttu-id="19857-102">既存のマップを追加する方法</span><span class="sxs-lookup"><span data-stu-id="19857-102">How to Add Existing Maps</span></span>
<span data-ttu-id="19857-103">既存のマップを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="19857-103">There may be times when you want to add an existing map to a BizTalk project.</span></span> <span data-ttu-id="19857-104">この操作を行う前に、マップの送信元スキーマおよび送信先スキーマがマップを追加する BizTalk プロジェクトに含まれている (または対応する .NET アセンブリによって参照されている) ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="19857-104">Before doing so, you must ensure that the source and destination schemas of the map are included in the BizTalk project to which you are adding the map; or, referenced by the corresponding .NET assembly.</span></span>  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a><span data-ttu-id="19857-105">既存のマップを BizTalk プロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="19857-105">To add an existing map to a BizTalk project</span></span>  
  
1. <span data-ttu-id="19857-106">ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="19857-106">Right-click a BizTalk project in Solution Explorer, point to **Add**, and then click **Existing Item**.</span></span>  
  
2. <span data-ttu-id="19857-107">**既存項目の追加** ダイアログ ボックスで、追加で選択しをクリックするマップを含むフォルダーを参照し**追加**します。</span><span class="sxs-lookup"><span data-stu-id="19857-107">In the **Add Existing Item** dialog box, browse to the folder containing the map to be added, select it, and then click **Add**.</span></span>  
  
    <span data-ttu-id="19857-108">マップは、BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="19857-108">The map opens in BizTalk Mapper.</span></span> <span data-ttu-id="19857-109">また、新しく追加したマップは、現在の BizTalk プロジェクトの子としてソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19857-109">The newly added map also appears as a child of the current BizTalk project in Solution Explorer.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="19857-110">BizTalk プロジェクト フォルダー以外のフォルダーを参照すると、追加したマップのコピーがプロジェクト フォルダーに作成されます。マップのこのコピーがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="19857-110">If you browsed to a folder other than the BizTalk project folder, a copy of the map you added was created in the project folder, and it was this copy of the map that was added to the project.</span></span> <span data-ttu-id="19857-111">マップに対するその後の変更は、このコピーに対して行われます。他のフォルダーの元のマップには行われません。</span><span class="sxs-lookup"><span data-stu-id="19857-111">Subsequent changes to the map are made to this copy, not to the original map in the other folder.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="19857-112">BizTalk マップは、BizTalk マッパー (Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルにホストされている) によってのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="19857-112">BizTalk maps can only be opened by BizTalk Mapper, which is hosted within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="19857-113">Windows エクスプローラーのマップをダブルクリックして、対応するスキーマが正常に読み込まれた場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の新しいインスタンスが開き、マップが BizTalk マッパーで開かれます。</span><span class="sxs-lookup"><span data-stu-id="19857-113">If you double-click a map in Windows Explorer, a new instance of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will be opened, and then the map will be opened by BizTalk Mapper, provided the corresponding schemas are loaded properly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="19857-114">既存のマップにカスタム Functoid が含まれる場合は、対応する DLL を "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions" フォルダーにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19857-114">If the existing map contains custom functoids, then the corresponding DLLs must be copied to the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span> <span data-ttu-id="19857-115">コピーしない場合、カスタム Functoid の読み込みに失敗するため、マップは読み込まれず、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="19857-115">Else, the map will not load and throws an error because of failure to load custom functoids.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19857-116">参照</span><span class="sxs-lookup"><span data-stu-id="19857-116">See Also</span></span>  
 <span data-ttu-id="19857-117">[プロジェクト内のマップを管理します。](../core/managing-maps-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="19857-117">[Managing Maps Within Projects](../core/managing-maps-within-projects.md) </span></span>  
 [<span data-ttu-id="19857-118">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="19857-118">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)