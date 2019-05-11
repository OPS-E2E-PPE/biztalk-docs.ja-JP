---
title: その他のスキーマを使用するスキーマを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 729e956fc2598fb8c3bd75d2d2d8a9613e1e96ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385445"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a><span data-ttu-id="d2e54-102">その他のスキーマを使用するスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d2e54-102">How to Create Schemas That Use Other Schemas</span></span>
<span data-ttu-id="d2e54-103">XML スキーマ定義 (XSD) 言語は、別のスキーマ内の 1 つのスキーマを使用するために、3 つの異なるが、関連するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-103">XML Schema definition (XSD) language provides three different but related mechanisms for using one schema within another schema.</span></span> <span data-ttu-id="d2e54-104">これらのメカニズムは、スキーマ、スキーマのインクルード、およびスキーマを再定義をインポートしています。</span><span class="sxs-lookup"><span data-stu-id="d2e54-104">These mechanisms are importing a schema, including a schema, and redefining a schema.</span></span> <span data-ttu-id="d2e54-105">これらのメカニズムとどのように異なるかの簡単な概要を参照してください。[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-105">For a brief summary of these mechanisms and how they differ, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span> <span data-ttu-id="d2e54-106">詳細については、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)XSD 入門と仕様へのリンク。</span><span class="sxs-lookup"><span data-stu-id="d2e54-106">For detailed information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md) for links to the XSD primer and specifications.</span></span>  
  
 <span data-ttu-id="d2e54-107">このトピックでは、インポート、インクルード、および再定義するその他のスキーマを開発するのに必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-107">This topic describes the steps required to import, include, and redefine other schemas within the schema you are developing.</span></span>  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a><span data-ttu-id="d2e54-108">インポート、インクルード、または別のスキーマ内の 1 つのスキーマを再定義するには</span><span class="sxs-lookup"><span data-stu-id="d2e54-108">To import, include, or redefine one schema within another schema</span></span>  
  
1. <span data-ttu-id="d2e54-109">BizTalk エディターでは、インポート、インクルード、または別のスキーマを再定義するスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2e54-109">In BizTalk Editor, open the schema to which you want to import, include, or redefine another schema.</span></span> <span data-ttu-id="d2e54-110">ソリューション エクスプ ローラーでダブルクリックして、スキーマを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d2e54-110">You can open a schema by double-clicking it in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="d2e54-111">選択、**スキーマ**スキーマ ツリー ビューの上部にあるノード。</span><span class="sxs-lookup"><span data-stu-id="d2e54-111">Select the **Schema** node at the top of the schema tree view.</span></span>  
  
3. <span data-ttu-id="d2e54-112">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2e54-112">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
4. <span data-ttu-id="d2e54-113">プロパティ ウィンドウで、 **詳細設定**  カテゴリの値の部分で、 **Imports**プロパティ、省略記号をクリックします (**...**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2e54-113">In the Properties window, in the **Advanced** category, in the value portion of the **Imports** property, click the ellipsis (**...**) button.</span></span>  
  
5. <span data-ttu-id="d2e54-114">**Imports** ] ダイアログ ボックスで、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、 **XSD Include**、または**XSD再定義**し、必要に応じて、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-114">In the **Imports** dialog box, in the **Import New Schema as** list, select **XSD Import**, **XSD Include**, or **XSD Redefine**, as appropriate, and then click **Add**.</span></span>  
  
6. <span data-ttu-id="d2e54-115">**BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**、プロジェクト ツリー内のノードは、インポート、インクルード、または再定義、および をクリックするスキーマを選択します。 **OK**。</span><span class="sxs-lookup"><span data-stu-id="d2e54-115">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the project tree, select the schema that you want to import, include, or redefine, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="d2e54-116">**インポート**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="d2e54-116">In the **Imports** dialog box, click **OK**.</span></span>  
  
    <span data-ttu-id="d2e54-117">インポートするを実装するために適切な XSD ディレクティブがインクルード、または操作を再定義に追加されます、**スキーマ**要素など、新しい XSD ビューで**インポート**、 **を含める**、または**redefine**に応じての要素。</span><span class="sxs-lookup"><span data-stu-id="d2e54-117">The appropriate XSD directives to implement the import, include, or redefine operation are added to the **schema** element in the XSD view, including a new **import**, **include**, or **redefine** element, as appropriate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e54-118">名前空間の要件に関しての違いなど、これらの 3 つのメカニズムのさまざまな目的を理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d2e54-118">Make sure you understand the different purposes of these three mechanisms, such as how they differ with respect to namespace requirements.</span></span> <span data-ttu-id="d2e54-119">常に以前にインポートされた、含まれる、または再定義されたスキーマを削除して、その他の 2 つのメカニズムのいずれかがによってどの程度そのスキーマを参照している場合、それに応じて、スキーマを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2e54-119">You can always delete a previously imported, included, or redefined schema and then use one of the other two mechanisms, but depending on how extensively you have referenced that schema, you may need to rework your schema accordingly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e54-120">インポート、インクルード、およびインポートへの参照によって別のスキーマの動作内の 1 つのスキーマを再定義する XSD のメカニズムは含まれている場合、またはスキーマを再定義します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-120">The XSD mechanism for importing, including, and redefining one schema within another schema works by reference to the imported, included, or redefined schema.</span></span> <span data-ttu-id="d2e54-121">つまり変更を行う場合、インポート、または再定義されたスキーマに変更をインポートを含むスキーマに反映されます包含、または参照を再定義します。</span><span class="sxs-lookup"><span data-stu-id="d2e54-121">This means that if you make a change to the imported, included, or redefined schema, that change will be reflected in the schema containing the import, include, or redefine reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e54-122">参照</span><span class="sxs-lookup"><span data-stu-id="d2e54-122">See Also</span></span>  
 <span data-ttu-id="d2e54-123">[プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="d2e54-123">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="d2e54-124">別のノードまたは種類への参照を作成する方法</span><span class="sxs-lookup"><span data-stu-id="d2e54-124">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)