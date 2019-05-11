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
ms.openlocfilehash: 13944689885ea504679591fcaabb2f442c486de1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334845"
---
# <a name="how-to-save-rename-and-close-schemas"></a><span data-ttu-id="8ccd6-102">保存、名前の変更、およびスキーマを終了する方法</span><span class="sxs-lookup"><span data-stu-id="8ccd6-102">How to Save, Rename, and Close Schemas</span></span>
<span data-ttu-id="8ccd6-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマの XML スキーマ定義 (XSD) 言語ファイルをおよび .xsd の拡張子を持つファイル システム上に存在します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], schemas are XML Schema definition (XSD) language files and reside on the file system with .xsd extensions.</span></span> <span data-ttu-id="8ccd6-104">BizTalk エディターを使用してスキーマを開発してスキーマ ファイルを閉じて保存する必要があります定期的に場合によっては、それらの名前を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-104">When you use BizTalk Editor to develop schemas, you will routinely need to save and close schema files, and occasionally you may need to rename them.</span></span> <span data-ttu-id="8ccd6-105">このトピックでは、これらの基本操作の実行に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-105">This topic describes the steps required to perform these basic operations.</span></span>  
  
### <a name="to-save-a-schema"></a><span data-ttu-id="8ccd6-106">スキーマを保存するには</span><span class="sxs-lookup"><span data-stu-id="8ccd6-106">To save a schema</span></span>  
  
1. <span data-ttu-id="8ccd6-107">必要に応じて、Microsoft では、メイン編集ウィンドウの上部にある適切なタブをクリックして、保存するスキーマの BizTalk エディターをアクティブ化[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-107">If necessary, activate BizTalk Editor for the schema to be saved by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="8ccd6-108">**ファイル** メニューのをクリックして \* \* 保存 *\<名前のスキーマ\>* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-108">On the **File** menu, click \*\*Save \*\<Name of Schema\>\*\*\*.</span></span>  
  
    <span data-ttu-id="8ccd6-109">場合は、スキーマには、変更が保存されていませんが、メイン編集ウィンドウの上部にあるタブに表示される名前は不要になった 未保存の変更を示すために使用されるアスタリスク (\*) で終了します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-109">If the schema had unsaved changes, its name as displayed on the tab at the top of the main editing window will no longer end with an asterisk (\*), which is used to indicate unsaved changes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ccd6-110">クリックして、新しい名前でスキーマを保存する\**保存*\<スキーマの名前\>\* として**上、**ファイル\*\*メニュー。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-110">You can save the schema under a new name by clicking **Save *\<Name of Schema\>* As** on the **File** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ccd6-111">スキーマを保存するには、プロジェクト内をクリックして変更されたすべての項目の保存の一部として**すべてを保存**上、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-111">You can save the schema as part of saving all changed items in the project by clicking **Save All** on the **File** menu.</span></span>  
  
#### <a name="to-rename-a-schema"></a><span data-ttu-id="8ccd6-112">スキーマの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="8ccd6-112">To rename a schema</span></span>  
  
1.  <span data-ttu-id="8ccd6-113">ソリューション エクスプ ローラーで、クリックして、名前を変更するスキーマを右クリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-113">In Solution Explorer, right-click the schema that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="8ccd6-114">ソリューション エクスプ ローラーでスキーマの場所に表示される編集ボックスで、スキーマの新しい名前を入力や、既存の名前を変更し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-114">In the editing box that appears in the location of the schema in Solution Explorer, type the new name for the schema, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ccd6-115">変更することも、**型名**の名前を変更するときにスキーマ。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-115">You may also want to change the **Type Name** of the schema when you rename.</span></span> <span data-ttu-id="8ccd6-116">変更する、**型名**を選択して、**スキーマ**ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-116">You change the **Type Name** by selecting the **schema** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ccd6-117">別のスキーマで使用されている任意のスキーマの名前を変更する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-117">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="8ccd6-118">これには、スキーマに含まれる、インポート、または再定義されているプロモーションが確立されて既にプロパティ スキーマおよびその他のスキーマによってが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-118">This includes schemas that have been included, imported, or redefined by other schemas, as well as property schemas for which promotions have already been established.</span></span> <span data-ttu-id="8ccd6-119">これを行う場合、使用されているスキーマが含まれている名前に正確なされなくなるために、変更されたスキーマを検索できません。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-119">If you do so, the schema that is being used will not be able to find the renamed schema because the name it contains will no longer be accurate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ccd6-120">特定の名前のスキーマ ファイルなどのプロジェクト メンバー ファイルなる競合によってコンパイル エラー c# 予約語で ("System") などと.net Framework 型と名前空間名。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-120">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as "System").</span></span> <span data-ttu-id="8ccd6-121">スキーマの例には、schema.xsd、XmlContent、および Rootnode が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-121">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="8ccd6-122">これは、ため、**型名**プロパティの既定値の基本 (拡張機能) の部分、**ファイル名**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-122">This is because the **Type Name** property defaults to the base (non-extension) portion of the **Filename** property.</span></span> <span data-ttu-id="8ccd6-123">この種のコンパイル エラーを回避するには、値を明示的に変更することで、**型名**プロパティを競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-123">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
#### <a name="to-close-a-schema"></a><span data-ttu-id="8ccd6-124">スキーマを閉じる</span><span class="sxs-lookup"><span data-stu-id="8ccd6-124">To close a schema</span></span>  
  
1. <span data-ttu-id="8ccd6-125">必要に応じて、Microsoft では、メイン編集ウィンドウの上部にある適切なタブをクリックして、終了するスキーマの BizTalk エディターをアクティブ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-125">If necessary, activate BizTalk Editor for the schema to be closed by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="8ccd6-126">**[ファイル]** メニューの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-126">On the **File** menu, click **Close**.</span></span>  
  
    <span data-ttu-id="8ccd6-127">閉じられているスキーマの BizTalk エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8ccd6-127">BizTalk Editor closes for the schema that has been closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ccd6-128">参照</span><span class="sxs-lookup"><span data-stu-id="8ccd6-128">See Also</span></span>  
 [<span data-ttu-id="8ccd6-129">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="8ccd6-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)