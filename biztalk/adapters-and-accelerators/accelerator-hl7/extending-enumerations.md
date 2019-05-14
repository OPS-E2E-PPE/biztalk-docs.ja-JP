---
title: 列挙の拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e8e5ab2b5072679e9d29f1c13f58c554e41c93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268058"
---
# <a name="extending-enumerations"></a><span data-ttu-id="46ad9-102">列挙の拡張</span><span class="sxs-lookup"><span data-stu-id="46ad9-102">Extending Enumerations</span></span>
<span data-ttu-id="46ad9-103">HL7 メッセージの本文、受信確認、およびメッセージ本文のスキーマのフィールド、セグメント、およびデータのさまざまな種類の値を確立するための列挙体には、値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="46ad9-103">You can add values to the enumerations that establish accepted values for many fields, segments, and data types in HL7 message body, acknowledgment, and message body schemas.</span></span> <span data-ttu-id="46ad9-104">ユーザーが作業して、HL7 バージョン用の一般的なテーブル値スキーマ ファイルの特定のテーブル内の値のセットを変更する必要があります (、 **Tablevalues_\<**<em>バージョン</em> **\>.xsd**スキーマ ファイル)。</span><span class="sxs-lookup"><span data-stu-id="46ad9-104">This involves changing the set of values in a specific table in the common table values schema file for the HL7 version in which you are working (the **Tablevalues_\<**<em>version</em>**\>.xsd** schema file).</span></span>  
  
 <span data-ttu-id="46ad9-105">追加する列挙体にメッセージのヘッダー スキーマ用の別の方法でメッセージ本文のスキーマなどの他のスキーマの場合。</span><span class="sxs-lookup"><span data-stu-id="46ad9-105">You add to the enumeration in a different way for the message header schema than you do in other schemas, such as the message body schema.</span></span> <span data-ttu-id="46ad9-106">メッセージ ヘッダー スキーマ、MSH_25_GLO_DEF.xsd ファイル内のテーブルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46ad9-106">For the message header schema, you must change the table within the MSH_25_GLO_DEF.xsd file.</span></span> <span data-ttu-id="46ad9-107">テーブル値のスキーマ ファイル内のテーブルを変更する他のスキーマ (tablevalues_\<バージョン\>.xsd)。</span><span class="sxs-lookup"><span data-stu-id="46ad9-107">For other schemas, you change the table in the table values schema file (tablevalues_\<version\>.xsd).</span></span>  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a><span data-ttu-id="46ad9-108">テーブル値の一般的なスキーマ ファイルに列挙値を追加するには</span><span class="sxs-lookup"><span data-stu-id="46ad9-108">To add an enumeration value to the table values common schema file</span></span>  
  
1. <span data-ttu-id="46ad9-109">最初に追加する列挙体を含むテーブルを決定する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="46ad9-109">You first need to determine the table that contains the enumeration that you want to add to.</span></span> <span data-ttu-id="46ad9-110">ソリューション エクスプ ローラーの Visual Studio で、変更する要素が含まれているスキーマ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="46ad9-110">In Solution Explorer of Visual Studio, open the schema file that contains the element that you want to change.</span></span> <span data-ttu-id="46ad9-111">BizTalk エクスプローラで、フィールド要素の値を追加する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46ad9-111">In BizTalk Explorer, click the field element that you want to add a value for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ad9-112">テーブル値の一般的なスキーマ ファイル内の列挙型を変更すると、その列挙体を参照するすべてのオブジェクトが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="46ad9-112">When you change an enumeration in the table values common schema file, all objects that reference that enumeration are affected.</span></span>  
  
2. <span data-ttu-id="46ad9-113">**プロパティ**ウィンドウ内のテーブルの名前に注意してください、 **Base Data Type**フィールド。</span><span class="sxs-lookup"><span data-stu-id="46ad9-113">In the **Properties** pane, note the name of the table in the **Base Data Type** field.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ad9-114">テーブルが表示されない場合がある**Base Data Type**フィールド、および**Derived By**プロパティに設定されていない**Restricted**フィールドには、関連付けられている列挙体にありません.</span><span class="sxs-lookup"><span data-stu-id="46ad9-114">If there is no table listed in **Base Data Type** field, and the **Derived By** property is not set to **Restricted**, then the field does not have an enumeration associated with it.</span></span>  
  
3. <span data-ttu-id="46ad9-115">ソリューション エクスプ ローラーで開く、 **Tablevalues_\<**<em>バージョン</em>**\>.xsd**、 をクリックし、**開く**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-115">In Solution Explorer, open the **Tablevalues_\<**<em>version</em>**\>.xsd**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46ad9-116">変更する HL7 スキーマのバージョンごとに個別にこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46ad9-116">You must perform this procedure separately for each version of the HL7 schema that you want to change.</span></span>  
  
4. <span data-ttu-id="46ad9-117">BizTalk エディターでは、変更、およびそのテーブル ノードをクリックするテーブルを参照します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-117">In BizTalk Editor, browse to the table you want to change, and then click that table node.</span></span>  
  
5. <span data-ttu-id="46ad9-118">プロパティ ウィンドウで、**制限**セクションで、**列挙**、列挙エディターを開く省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="46ad9-118">In the Properties window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
6. <span data-ttu-id="46ad9-119">列挙エディターで、既存の値の一覧に新しい値を追加し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-119">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a><span data-ttu-id="46ad9-120">列挙値をメッセージ ヘッダーのスキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="46ad9-120">To add an enumeration value to a message header schema</span></span>  
  
1. <span data-ttu-id="46ad9-121">ソリューション エクスプ ローラーで、MSH_25_GLO_DEF スキーマを開くし、順にクリックします**開く**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-121">In Solution Explorer, open the MSH_25_GLO_DEF schema, and then click **Open**.</span></span>  
  
2. <span data-ttu-id="46ad9-122">右クリックし、 **MSH**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-122">Right-click the **MSH** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="46ad9-123">呼ばれる MSH フィールド ノードを追加**フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-123">adds a field node to MSH, called **Field**.</span></span> <span data-ttu-id="46ad9-124">クリックして**ENTER**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-124">Click **ENTER**.</span></span>  
  
3. <span data-ttu-id="46ad9-125">**プロパティ**ウィンドウで、をクリックして、**データ型**ノードのドロップダウン リストから、列挙値を追加するテーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-125">In the **Properties** window, click the **Data Type** node, then from the drop-down list, select the table to which you want to add the enumeration value.</span></span>  
  
4. <span data-ttu-id="46ad9-126">**プロパティ**ウィンドウで、**制限**セクションで、**列挙**、列挙型のエディターを開く省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="46ad9-126">In the **Properties** window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
5. <span data-ttu-id="46ad9-127">列挙エディターで、既存の値の一覧に新しい値を追加し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-127">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
    <span data-ttu-id="46ad9-128">追加すると、値の列挙の任意のノードなど、**フィールド**ノードで、そのテーブルを使用するすべてのオブジェクトのグローバルにその値を追加します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-128">When you add a value to the enumeration for any node, such as the **Field** node, you add that value globally for all objects that use that table.</span></span> <span data-ttu-id="46ad9-129">その結果、これを削除できる、**フィールド**ノード、および値テーブルに存在するされます。</span><span class="sxs-lookup"><span data-stu-id="46ad9-129">As a result, you can now delete the **Field** node, and the value will still be present for the table.</span></span> <span data-ttu-id="46ad9-130">これを確認するには、テーブルに BizTalk エディターの右側ウィンドウのスクロールを追加した値が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-130">You can verify this by scrolling in the right pane of BizTalk Editor to the table, and verifying that the value that you added is present.</span></span>  
  
6. <span data-ttu-id="46ad9-131">右クリックし、**フィールド**BizTalk エディターでノードをクリックして**削除**、順にクリックします**はい**します。</span><span class="sxs-lookup"><span data-stu-id="46ad9-131">Right-click the **Field** node in BizTalk Editor, click **Delete**, and then click **Yes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ad9-132">参照</span><span class="sxs-lookup"><span data-stu-id="46ad9-132">See Also</span></span>  
 <span data-ttu-id="46ad9-133">[テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="46ad9-133">[Table Values Common Schemas](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span></span>  
 <span data-ttu-id="46ad9-134">[Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="46ad9-134">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="46ad9-135">[宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="46ad9-135">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="46ad9-136">[スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="46ad9-136">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="46ad9-137">[スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="46ad9-137">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 [<span data-ttu-id="46ad9-138">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="46ad9-138">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)