---
title: 他のスキーマを使用するスキーマを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f427e5cd8e3f82e57dc8926c6e00889e1c97afe9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249418"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a><span data-ttu-id="a3b8b-102">他のスキーマを使用するスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a3b8b-102">How to Create Schemas That Use Other Schemas</span></span>
<span data-ttu-id="a3b8b-103">XSD (XML Schema Definition) 言語には、あるスキーマを他のスキーマで使用するためのメカニズムが 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-103">XML Schema definition (XSD) language provides three different but related mechanisms for using one schema within another schema.</span></span> <span data-ttu-id="a3b8b-104">スキーマのインポート、スキーマのインクルード、および、スキーマの再定義です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-104">These mechanisms are importing a schema, including a schema, and redefining a schema.</span></span> <span data-ttu-id="a3b8b-105">これらのメカニズムと違いの簡単な要約を参照してください。[スキーマを使用して他のスキーマを](../core/schemas-that-use-other-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-105">For a brief summary of these mechanisms and how they differ, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span> <span data-ttu-id="a3b8b-106">詳細については、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)XSD 入門および仕様へのリンク用です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-106">For detailed information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md) for links to the XSD primer and specifications.</span></span>  
  
 <span data-ttu-id="a3b8b-107">このトピックでは、作成中のスキーマ内で他のスキーマをインポート、インクルード、および再定義する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-107">This topic describes the steps required to import, include, and redefine other schemas within the schema you are developing.</span></span>  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a><span data-ttu-id="a3b8b-108">スキーマ内で他のスキーマをインポート、インクルードまたは再定義するには</span><span class="sxs-lookup"><span data-stu-id="a3b8b-108">To import, include, or redefine one schema within another schema</span></span>  
  
1.  <span data-ttu-id="a3b8b-109">BizTalk エディターで、他のスキーマをインポート、インクルード、または再定義するスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-109">In BizTalk Editor, open the schema to which you want to import, include, or redefine another schema.</span></span> <span data-ttu-id="a3b8b-110">スキーマを開くには、ソリューション エクスプローラーで、目的のスキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-110">You can open a schema by double-clicking it in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a3b8b-111">選択、**スキーマ**スキーマ ツリー ビューの上部にあるノード。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-111">Select the **Schema** node at the top of the schema tree view.</span></span>  
  
3.  <span data-ttu-id="a3b8b-112">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-112">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
4.  <span data-ttu-id="a3b8b-113">プロパティ ウィンドウでの**詳細設定**  カテゴリの値の部分で、 **Imports**プロパティ、省略記号ボタンをクリックして (**...**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-113">In the Properties window, in the **Advanced** category, in the value portion of the **Imports** property, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="a3b8b-114">**Imports** ] ダイアログ ボックスで、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、 **XSD Include**、または**XSD再定義**、必要に応じて、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-114">In the **Imports** dialog box, in the **Import New Schema as** list, select **XSD Import**, **XSD Include**, or **XSD Redefine**, as appropriate, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="a3b8b-115">**BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**プロジェクト ツリー内のノードは、インポート、インクルード、または再定義、およびをクリックするスキーマを選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-115">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the project tree, select the schema that you want to import, include, or redefine, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a3b8b-116">**Imports**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-116">In the **Imports** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="a3b8b-117">インポートを実装する適切な XSD ディレクティブは、包含、または操作を再定義に追加されます、**スキーマ**XSD ビューで、たとえば、新しい要素**インポート**、 **を含める**、または**redefine**に応じての要素。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-117">The appropriate XSD directives to implement the import, include, or redefine operation are added to the **schema** element in the XSD view, including a new **import**, **include**, or **redefine** element, as appropriate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a3b8b-118">これら 3 つのメカニズムの目的について、それぞれの相違点 (名前空間の要件に関連した動作上の違いなど) を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-118">Make sure you understand the different purposes of these three mechanisms, such as how they differ with respect to namespace requirements.</span></span> <span data-ttu-id="a3b8b-119">既にインポート、インクルード、または再定義されているスキーマはいつでも削除し、他のメカニズムのいずれかに切り替えることができます。ただし、スキーマを参照している範囲によっては、それに応じた修正をスキーマに対して行わなければならない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-119">You can always delete a previously imported, included, or redefined schema and then use one of the other two mechanisms, but depending on how extensively you have referenced that schema, you may need to rework your schema accordingly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a3b8b-120">あるスキーマを別のスキーマ内でインポート、インクルード、または再定義する XSD のメカニズムは、インポート、インクルード、または再定義されているスキーマを参照することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-120">The XSD mechanism for importing, including, and redefining one schema within another schema works by reference to the imported, included, or redefined schema.</span></span> <span data-ttu-id="a3b8b-121">つまり、インポート、インクルード、または再定義されたスキーマに変更を加えた場合、それを参照しているスキーマにも反映されます。</span><span class="sxs-lookup"><span data-stu-id="a3b8b-121">This means that if you make a change to the imported, included, or redefined schema, that change will be reflected in the schema containing the import, include, or redefine reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b8b-122">参照</span><span class="sxs-lookup"><span data-stu-id="a3b8b-122">See Also</span></span>  
 <span data-ttu-id="a3b8b-123">[プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="a3b8b-123">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="a3b8b-124">別のノードまたは種類への参照を作成する方法</span><span class="sxs-lookup"><span data-stu-id="a3b8b-124">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)