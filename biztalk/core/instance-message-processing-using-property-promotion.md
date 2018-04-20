---
title: プロパティの昇格を使用してメッセージの処理をインスタンス化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="instance-message-processing-using-property-promotion"></a><span data-ttu-id="b11d5-102">プロパティの昇格を使用したインスタンス メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="b11d5-102">Instance Message Processing Using Property Promotion</span></span>
<span data-ttu-id="b11d5-103">使用してプロパティの昇格、 **プロパティ フィールド** メソッド、プロパティ スキーマの作成が必要です。</span><span class="sxs-lookup"><span data-stu-id="b11d5-103">Promoting properties by using the **Property Field** method requires the creation of a property schema.</span></span> <span data-ttu-id="b11d5-104">プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="b11d5-104">For more information about creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span> <span data-ttu-id="b11d5-105">すべてのプロパティの昇格では使用すると、 **プロパティの昇格** を使用してアクセス可能なダイアログ ボックス、 **プロパティの昇格** のプロパティ、 **スキーマ** メッセージ スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="b11d5-105">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b11d5-106">昇格プロパティにアクセスして使用するには、プロパティを昇格するパイプラインを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b11d5-106">You must choose a pipeline that promotes properties in order to access and use the promote properties.</span></span> <span data-ttu-id="b11d5-107">たとえば、PassthruReceive パイプラインを使用する場合はプロパティは昇格されないため、コンテンツ ベースのルーティングおよびその他の機能は正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="b11d5-107">For example, if you use the PassthruReceive pipeline, no properties will be promoted; as a result, content-based routing and other functionality will not work as expected.</span></span>  
  
 <span data-ttu-id="b11d5-108">**プロパティの昇格**  ダイアログ ボックスで確認、 **プロパティ フィールド**  ダイアログ ボックスの右側にタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-108">In the **Promote Properties** dialog box, make sure the **Property Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="b11d5-109">次に、プロパティ スキーマの一覧の上部で、適切なプロパティ スキーマが含まれていることを確認、 **プロパティ フィールド**  タブをクリックします。必要に応じて、使用してフォルダー ボタンを使用して、適切なプロパティ スキーマを選択する、 **BizTalk 型の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b11d5-109">Next, ensure the appropriate property schema is included in the Property Schemas List at the top of the **Property Fields** tab. If necessary, use the folder button to select the appropriate property schema by using the **BizTalk Type Picker** dialog box.</span></span> <span data-ttu-id="b11d5-110">次に、[を検索して選択] ダイアログ ボックスの左側にあるスキーマ ツリーでノードを展開して、 **フィールド要素** ノードまたは **フィールド属性** クリックして、プロパティ フィールドとして昇格するノードを **追加**します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-110">Next, expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a property field, and then click **Add**.</span></span> <span data-ttu-id="b11d5-111">ドロップ ダウン リストの最後に、使用、 **プロパティ** の列、 **プロパティ フィールド ディクショナリ** を選択するテーブル、 **フィールド要素** に昇格させたプロパティを関連付けるプロパティ スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b11d5-111">Finally, use the drop-down list in the **Property** column of the **Property-Fields dictionary** table to select a **Field Element** node in a property schema with which to associate the promoted property.</span></span> <span data-ttu-id="b11d5-112">操作手順については、プロパティ フィールドを使用するプロパティの昇格、**プロパティの昇格** ダイアログ ボックスを参照してください[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。</span><span class="sxs-lookup"><span data-stu-id="b11d5-112">For step-by-step instructions about promoting properties to property fields using the **Promote Properties** dialog ox, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b11d5-113">昇格することも、 **レコード** ノードを **フィールド要素** 場合に限り、プロパティ スキーマ内のノード、 **コンテンツ タイプ** のプロパティ、 **レコード** にノードが設定されている **SimpleContent**します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-113">You can also promote a **Record** node to a **Field Element** node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b11d5-114">同じプロパティをスキーマ内で複数回昇格できます。ただし、これらの昇格が、それぞれ異なるルート ノードについて行われる場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="b11d5-114">The same property can be promoted multiple times within a schema as long as all of these promotions are performed under different root nodes.</span></span> <span data-ttu-id="b11d5-115">これは、メッセージの検証は単一のルート ノードに対して行われ、そのルート ノードで昇格したプロパティだけが実行時に評価されるためです。</span><span class="sxs-lookup"><span data-stu-id="b11d5-115">This is because the message is validated against a single root node and only properties promoted under that root node are evaluated at run time.</span></span>  
  
 <span data-ttu-id="b11d5-116">削除する、 **フィールド要素** ノードまたは **フィールド属性** プロパティ フィールドとして昇格するプロパティのセットからのノードで昇格させたプロパティを選択して、 **プロパティ フィールド ディクショナリ** テーブルに、 **プロパティ フィールド** タブをクリックし、をクリックし、 **削除**します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-116">To remove a **Field Element** node or **Field Attribute** node from the set of properties being promoted as property fields, select the promoted property in the **Property-Fields dictionary** table on the **Property Fields** tab, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="b11d5-117">**ノード パス** 内の列、 **プロパティ フィールド ディクショナリ** テーブルは、昇格させたプロパティに対応するスキーマ ノードの XPath を示します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-117">The **Node Path** column in the **Property-Fields dictionary** table shows the XPath to the schema node corresponding to the promoted property.</span></span> <span data-ttu-id="b11d5-118">この値を編集するにを使用して直接、 **インスタンス XPath の編集**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b11d5-118">You can edit this value directly by using the **Edit Instance XPath** dialog box.</span></span> <span data-ttu-id="b11d5-119">省略記号ボタンをクリックして、このダイアログ ボックスを開くことができます (**...**) そのセルを選択すると、対応するセルの右端に表示されるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b11d5-119">You can open this dialog box by clicking the ellipsis (**...**) button that appears at the right end of the corresponding cell when you select that cell.</span></span> <span data-ttu-id="b11d5-120">ただし、BizTalk エディターで解決できない XPath が適切な検証操作の妨げとなる場合があるので、XPath の値を直接編集するときは注意してください。</span><span class="sxs-lookup"><span data-stu-id="b11d5-120">Care must be taken when editing XPath values directly because XPaths that cannot be resolved by BizTalk Editor will prevent proper validation operations.</span></span>  
  
 <span data-ttu-id="b11d5-121">BizTalk エディターを使用してプロパティを昇格する場合に効率化されたコマンドもでは、 **プロパティ フィールド** メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="b11d5-121">BizTalk Editor also provides a streamlined command for promoting properties using the **Property Field** mechanism.</span></span> <span data-ttu-id="b11d5-122">このコマンドはクイック昇格と呼ばれ、使用して設定できることをお勧めします **昇格と #124 文字です。クイック昇格** コマンド、BizTalk メニューとショートカット メニューをします。</span><span class="sxs-lookup"><span data-stu-id="b11d5-122">This command is called Quick Promotion, and it is available using the **Promote &#124; Quick Promotion** command on the BizTalk and shortcut menus.</span></span> <span data-ttu-id="b11d5-123">このコマンドは、選択した昇格 **フィールド** ノード (または **レコード** ノード) で指定されたプロパティ スキーマに自動的に作成されるプロパティ フィールドに、 **プロパティ スキーマ名の既定の** プロパティに、 **プロパティ ページ** を含むスキーマのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b11d5-123">This command promotes the selected **Field** node (or **Record** node) to a property field that is automatically created in the property schema specified by the **Default Property Schema Name** property in the **Property Pages** dialog box for the containing schema.</span></span> <span data-ttu-id="b11d5-124">クイック昇格 コマンドを使用して、プロパティ フィールドにプロパティを昇格させる方法の詳細な手順については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。</span><span class="sxs-lookup"><span data-stu-id="b11d5-124">For step-by-step instructions about promoting properties to property fields using the Quick Promotion command, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="b11d5-125">プロパティ フィールドのメカニズムを使用してプロパティを昇格させると、XSD (XML Schema Definition) 言語による 2 つのフラグメントが、XSD 表記のメッセージ スキーマに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b11d5-125">When you promote a property by using the property field mechanism, two XML Schema definition (XSD) language fragments are added to the XSD representation of the message schema.</span></span> <span data-ttu-id="b11d5-126">最初の XSD フラグメントは、関連付けられる注釈フラグメント、 **スキーマ** 要素を次の例に示すように、対応するプロパティ スキーマを識別します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-126">The first XSD fragment is an annotation fragment associated with the **schema** element that identifies the corresponding property schema, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 <span data-ttu-id="b11d5-127">2 番目の XSD フラグメントは、関連付けられる注釈フラグメント、 **ルート** (かどうか、名前が変更されました) に関係なく要素を識別する、 **フィールド要素** ノードまたは **フィールド属性** プロパティを使用して昇格されたノードの値フィールドのメカニズムは、例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b11d5-127">The second XSD fragment is an annotation fragment associated with the **Root** element (regardless of whether it has been renamed) that identifies the **Field Element** node or **Field Attribute** node values that have been promoted by using the property field mechanism, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b11d5-128">参照</span><span class="sxs-lookup"><span data-stu-id="b11d5-128">See Also</span></span>  
 <span data-ttu-id="b11d5-129">[メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="b11d5-129">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="b11d5-130">プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="b11d5-130">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)