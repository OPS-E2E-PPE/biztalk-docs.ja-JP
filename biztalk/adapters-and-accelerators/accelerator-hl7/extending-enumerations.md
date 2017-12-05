---
title: "列挙型を拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2abb040d79f0c9312a8761289c0bf6252fef2f3a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="extending-enumerations"></a><span data-ttu-id="52e53-102">列挙型を拡張します。</span><span class="sxs-lookup"><span data-stu-id="52e53-102">Extending Enumerations</span></span>
<span data-ttu-id="52e53-103">HL7 メッセージ本文、受信確認、およびメッセージ本文のスキーマで多くのフィールド、セグメント、およびデータ型を指定できる値を確立する列挙体に値を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="52e53-103">You can add values to the enumerations that establish accepted values for many fields, segments, and data types in HL7 message body, acknowledgment, and message body schemas.</span></span> <span data-ttu-id="52e53-104">一般的なテーブル値スキーマ ファイルで作業している HL7 のバージョンについては、特定のテーブル内の値のセットを変更する必要があります (、 **Tablevalues_\<***バージョン* **\>.xsd**スキーマ ファイル)。</span><span class="sxs-lookup"><span data-stu-id="52e53-104">This involves changing the set of values in a specific table in the common table values schema file for the HL7 version in which you are working (the **Tablevalues_\<***version***\>.xsd** schema file).</span></span>  
  
 <span data-ttu-id="52e53-105">追加する列挙体に、メッセージ ヘッダーのスキーマを別の方法でメッセージのボディ スキーマなどの他のスキーマで行うよりもします。</span><span class="sxs-lookup"><span data-stu-id="52e53-105">You add to the enumeration in a different way for the message header schema than you do in other schemas, such as the message body schema.</span></span> <span data-ttu-id="52e53-106">メッセージ ヘッダー スキーマ用には、MSH_25_GLO_DEF.xsd ファイル内のテーブルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e53-106">For the message header schema, you must change the table within the MSH_25_GLO_DEF.xsd file.</span></span> <span data-ttu-id="52e53-107">テーブル値のスキーマ ファイル内のテーブルを変更する他のスキーマ (tablevalues_\<バージョン\>.xsd)。</span><span class="sxs-lookup"><span data-stu-id="52e53-107">For other schemas, you change the table in the table values schema file (tablevalues_\<version\>.xsd).</span></span>  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a><span data-ttu-id="52e53-108">テーブル値の共通スキーマ ファイルに列挙値を追加するには</span><span class="sxs-lookup"><span data-stu-id="52e53-108">To add an enumeration value to the table values common schema file</span></span>  
  
1.  <span data-ttu-id="52e53-109">最初に追加する列挙体を含むテーブルを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e53-109">You first need to determine the table that contains the enumeration that you want to add to.</span></span> <span data-ttu-id="52e53-110">ソリューション エクスプ ローラーの Visual Studio で、変更する要素が含まれたスキーマ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52e53-110">In Solution Explorer of Visual Studio, open the schema file that contains the element that you want to change.</span></span> <span data-ttu-id="52e53-111">BizTalk エクスプ ローラーでの値を追加するフィールドの要素をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52e53-111">In BizTalk Explorer, click the field element that you want to add a value for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52e53-112">テーブル値の共通スキーマ ファイル内の列挙型を変更すると、その列挙体を参照するすべてのオブジェクトが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="52e53-112">When you change an enumeration in the table values common schema file, all objects that reference that enumeration are affected.</span></span>  
  
2.  <span data-ttu-id="52e53-113">**プロパティ**ウィンドウ内のテーブルの名前に注意してください、 **Base Data Type**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="52e53-113">In the **Properties** pane, note the name of the table in the **Base Data Type** field.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52e53-114">テーブルが表示されない場合がある**Base Data Type**フィールド、および**Derived By**プロパティに設定されていない**Restricted**フィールドには、関連付けられている列挙値はありませんし、.</span><span class="sxs-lookup"><span data-stu-id="52e53-114">If there is no table listed in **Base Data Type** field, and the **Derived By** property is not set to **Restricted**, then the field does not have an enumeration associated with it.</span></span>  
  
3.  <span data-ttu-id="52e53-115">ソリューション エクスプ ローラーで開く、 **Tablevalues_\<***バージョン***\>.xsd**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-115">In Solution Explorer, open the **Tablevalues_\<***version***\>.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52e53-116">変更する HL7 スキーマのバージョンごとに個別にこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e53-116">You must perform this procedure separately for each version of the HL7 schema that you want to change.</span></span>  
  
4.  <span data-ttu-id="52e53-117">BizTalk エディターでは、変更、およびそのテーブル ノードをクリックするテーブルを参照します。</span><span class="sxs-lookup"><span data-stu-id="52e53-117">In BizTalk Editor, browse to the table you want to change, and then click that table node.</span></span>  
  
5.  <span data-ttu-id="52e53-118">[プロパティ] ウィンドウで、**制限**セクションで、をクリックして**列挙**、列挙エディタを開くの省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52e53-118">In the Properties window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
6.  <span data-ttu-id="52e53-119">列挙エディターで、既存の値の一覧に新しい値を追加し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-119">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a><span data-ttu-id="52e53-120">列挙値をメッセージ ヘッダーのスキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="52e53-120">To add an enumeration value to a message header schema</span></span>  
  
1.  <span data-ttu-id="52e53-121">ソリューション エクスプ ローラーで、MSH_25_GLO_DEF スキーマを開き、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-121">In Solution Explorer, open the MSH_25_GLO_DEF schema, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="52e53-122">右クリックし、 **MSH**に**スキーマ ノードの挿入**、順にクリック**子フィールド要素**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-122">Right-click the **MSH** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="52e53-123">MSH と呼ばれるフィールド ノードを追加**フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-123"> adds a field node to MSH, called **Field**.</span></span> <span data-ttu-id="52e53-124">をクリックして**ENTER**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-124">Click **ENTER**.</span></span>  
  
3.  <span data-ttu-id="52e53-125">**プロパティ**ウィンドウで、をクリックして、**データ型**ノード、し、ドロップダウン リストから、列挙値を追加するテーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52e53-125">In the **Properties** window, click the **Data Type** node, then from the drop-down list, select the table to which you want to add the enumeration value.</span></span>  
  
4.  <span data-ttu-id="52e53-126">**プロパティ**ウィンドウで、**制限**セクションで、**列挙**、列挙エディタを開くの省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52e53-126">In the **Properties** window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
5.  <span data-ttu-id="52e53-127">列挙エディターで、既存の値の一覧に新しい値を追加し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-127">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
     <span data-ttu-id="52e53-128">ときに値を追加する任意のノードを列挙するなど、**フィールド**ノード、そのテーブルを使用するすべてのオブジェクトに対してグローバルにその値を追加します。</span><span class="sxs-lookup"><span data-stu-id="52e53-128">When you add a value to the enumeration for any node, such as the **Field** node, you add that value globally for all objects that use that table.</span></span> <span data-ttu-id="52e53-129">結果として、これを削除できる、**フィールド**ノード、および値、テーブルの存在されます。</span><span class="sxs-lookup"><span data-stu-id="52e53-129">As a result, you can now delete the **Field** node, and the value will still be present for the table.</span></span> <span data-ttu-id="52e53-130">テーブルに BizTalk エディターの右側ウィンドウのスクロールして追加した値の存在を確認するには、これを確認できます。</span><span class="sxs-lookup"><span data-stu-id="52e53-130">You can verify this by scrolling in the right pane of BizTalk Editor to the table, and verifying that the value that you added is present.</span></span>  
  
6.  <span data-ttu-id="52e53-131">右クリックし、**フィールド**BizTalk エディターでノードをクリックして**削除**、順にクリック**はい**です。</span><span class="sxs-lookup"><span data-stu-id="52e53-131">Right-click the **Field** node in BizTalk Editor, click **Delete**, and then click **Yes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e53-132">参照</span><span class="sxs-lookup"><span data-stu-id="52e53-132">See Also</span></span>  
 <span data-ttu-id="52e53-133">[テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="52e53-133">[Table Values Common Schemas](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span></span>  
 <span data-ttu-id="52e53-134">[Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="52e53-134">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="52e53-135">[宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="52e53-135">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="52e53-136">[スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="52e53-136">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="52e53-137">[スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="52e53-137">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 [<span data-ttu-id="52e53-138">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="52e53-138">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)