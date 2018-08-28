---
title: 保存、名前の変更、およびスキーマを終了する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059a52bd3dd34669c5809653302c049eee92b96e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002907"
---
# <a name="how-to-save-rename-and-close-schemas"></a><span data-ttu-id="9fabd-102">スキーマの保存、名前変更、および終了の方法</span><span class="sxs-lookup"><span data-stu-id="9fabd-102">How to Save, Rename, and Close Schemas</span></span>
<span data-ttu-id="9fabd-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、スキーマは XSD (XML Schema Definition) 言語ファイルであり、ファイル システムに .xsd という拡張子で格納されます。</span><span class="sxs-lookup"><span data-stu-id="9fabd-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], schemas are XML Schema definition (XSD) language files and reside on the file system with .xsd extensions.</span></span> <span data-ttu-id="9fabd-104">BizTalk エディターを使用したスキーマの作成には、スキーマ ファイルの保存と終了、場合によっては、ファイル名の変更といった作業が常に伴います。</span><span class="sxs-lookup"><span data-stu-id="9fabd-104">When you use BizTalk Editor to develop schemas, you will routinely need to save and close schema files, and occasionally you may need to rename them.</span></span> <span data-ttu-id="9fabd-105">このトピックでは、こうした基本操作に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fabd-105">This topic describes the steps required to perform these basic operations.</span></span>  
  
### <a name="to-save-a-schema"></a><span data-ttu-id="9fabd-106">スキーマを保存するには</span><span class="sxs-lookup"><span data-stu-id="9fabd-106">To save a schema</span></span>  
  
1. <span data-ttu-id="9fabd-107">必要に応じて、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウ上部にある適切なタブをクリックして、保存するスキーマの BizTalk エディターをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="9fabd-107">If necessary, activate BizTalk Editor for the schema to be saved by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="9fabd-108">**ファイル** メニューのをクリックして * * 保存 *\<名前のスキーマ\>* * *。</span><span class="sxs-lookup"><span data-stu-id="9fabd-108">On the **File** menu, click **Save *\<Name of Schema\>***.</span></span>  
  
    <span data-ttu-id="9fabd-109">スキーマに対する変更がまだ保存されていなかった場合、スキーマを保存すると、メイン編集ウィンドウ上部のタブに表示される名前からアスタリスク (\*) が消えます。このアスタリスクは、変更内容が保存されていないことを示すマークです。</span><span class="sxs-lookup"><span data-stu-id="9fabd-109">If the schema had unsaved changes, its name as displayed on the tab at the top of the main editing window will no longer end with an asterisk (\*), which is used to indicate unsaved changes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fabd-110">クリックして、新しい名前でスキーマを保存する**保存*\<スキーマの名前\>* として**上、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="9fabd-110">You can save the schema under a new name by clicking **Save *\<Name of Schema\>* As** on the **File** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fabd-111">スキーマを保存するには、プロジェクト内をクリックして変更されたすべての項目の保存の一部として**すべてを保存**上、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="9fabd-111">You can save the schema as part of saving all changed items in the project by clicking **Save All** on the **File** menu.</span></span>  
  
#### <a name="to-rename-a-schema"></a><span data-ttu-id="9fabd-112">スキーマ名を変更するには</span><span class="sxs-lookup"><span data-stu-id="9fabd-112">To rename a schema</span></span>  
  
1.  <span data-ttu-id="9fabd-113">ソリューション エクスプ ローラーで、クリックして、名前を変更するスキーマを右クリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="9fabd-113">In Solution Explorer, right-click the schema that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="9fabd-114">ソリューション エクスプローラーで、スキーマの位置に表示された編集ボックスに新しいスキーマ名を入力するか、既存の名前を変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9fabd-114">In the editing box that appears in the location of the schema in Solution Explorer, type the new name for the schema, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fabd-115">変更することも、**型名**の名前を変更するときにスキーマ。</span><span class="sxs-lookup"><span data-stu-id="9fabd-115">You may also want to change the **Type Name** of the schema when you rename.</span></span> <span data-ttu-id="9fabd-116">変更する、**型名**を選択して、**スキーマ**ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="9fabd-116">You change the **Type Name** by selecting the **schema** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fabd-117">他のスキーマで使われているスキーマの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9fabd-117">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="9fabd-118">たとえば、他のスキーマによってインクルード、インポート、または再定義されたスキーマや、既に昇格が設定されたプロパティ スキーマなどです。</span><span class="sxs-lookup"><span data-stu-id="9fabd-118">This includes schemas that have been included, imported, or redefined by other schemas, as well as property schemas for which promotions have already been established.</span></span> <span data-ttu-id="9fabd-119">これらのスキーマの名前を変更した場合、使用されているスキーマが、名前の変更されたスキーマを見つけることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9fabd-119">If you do so, the schema that is being used will not be able to find the renamed schema because the name it contains will no longer be accurate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fabd-120">プロジェクトのメンバー ファイル (スキーマ ファイルなど) に特定の名前を使用すると、C# の予約語や NET Framework の型/名前空間名 ("System" など) との競合によってコンパイル エラーになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fabd-120">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as "System").</span></span> <span data-ttu-id="9fabd-121">このようなスキーマ名には、schema.xsd、XmlContent、RootNodes などがあります。</span><span class="sxs-lookup"><span data-stu-id="9fabd-121">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="9fabd-122">これは、ため、**型名**プロパティの既定値の基本 (拡張機能) の部分、**ファイル名**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9fabd-122">This is because the **Type Name** property defaults to the base (non-extension) portion of the **Filename** property.</span></span> <span data-ttu-id="9fabd-123">この種のコンパイル エラーを回避するには、値を明示的に変更することで、**型名**プロパティを競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="9fabd-123">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
#### <a name="to-close-a-schema"></a><span data-ttu-id="9fabd-124">スキーマを終了するには</span><span class="sxs-lookup"><span data-stu-id="9fabd-124">To close a schema</span></span>  
  
1. <span data-ttu-id="9fabd-125">必要に応じて、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウ上部にある適切なタブをクリックして、終了するスキーマの BizTalk エディターをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="9fabd-125">If necessary, activate BizTalk Editor for the schema to be closed by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="9fabd-126">**[ファイル]** メニューの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fabd-126">On the **File** menu, click **Close**.</span></span>  
  
    <span data-ttu-id="9fabd-127">BizTalk エディターによってスキーマが終了されます。</span><span class="sxs-lookup"><span data-stu-id="9fabd-127">BizTalk Editor closes for the schema that has been closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fabd-128">参照</span><span class="sxs-lookup"><span data-stu-id="9fabd-128">See Also</span></span>  
 [<span data-ttu-id="9fabd-129">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="9fabd-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)