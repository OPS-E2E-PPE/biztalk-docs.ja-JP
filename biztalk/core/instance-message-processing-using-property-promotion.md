---
title: インスタンスのプロパティの昇格を使用してメッセージの処理 |Microsoft Docs
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
ms.openlocfilehash: df619a7e8ec48565d06f16f4f8acbc5ac81c524f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331867"
---
# <a name="instance-message-processing-using-property-promotion"></a><span data-ttu-id="91135-102">プロパティの昇格を使用してインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="91135-102">Instance Message Processing Using Property Promotion</span></span>
<span data-ttu-id="91135-103">プロパティの昇格を使用して、**プロパティ フィールド**メソッド、プロパティ スキーマの作成が必要です。</span><span class="sxs-lookup"><span data-stu-id="91135-103">Promoting properties by using the **Property Field** method requires the creation of a property schema.</span></span> <span data-ttu-id="91135-104">プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="91135-104">For more information about creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span> <span data-ttu-id="91135-105">すべてのプロパティの昇格と同様、**プロパティの昇格** ダイアログ ボックスを使用してアクセスできますが、**プロパティの昇格**のプロパティ、**スキーマ**内のノードメッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="91135-105">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91135-106">昇格プロパティを使用してアクセスするためにプロパティを昇格するパイプラインを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91135-106">You must choose a pipeline that promotes properties in order to access and use the promote properties.</span></span> <span data-ttu-id="91135-107">たとえば、PassthruReceive パイプラインを使用する場合のプロパティは昇格されない;その結果、コンテンツ ベースのルーティングおよびその他の機能が正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="91135-107">For example, if you use the PassthruReceive pipeline, no properties will be promoted; as a result, content-based routing and other functionality will not work as expected.</span></span>  
  
 <span data-ttu-id="91135-108">**プロパティの昇格** ダイアログ ボックスに、ことを確認します、**プロパティ フィールド** ダイアログ ボックスの右側にあるタブが選択されています。</span><span class="sxs-lookup"><span data-stu-id="91135-108">In the **Promote Properties** dialog box, make sure the **Property Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="91135-109">次に、プロパティ スキーマの一覧の上部で、適切なプロパティ スキーマが含まれていることを確認、**プロパティ フィールド**タブ。必要に応じて、使用して、適切なプロパティ スキーマを選択するフォルダー ボタンを使用して、 **BizTalk 型の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="91135-109">Next, ensure the appropriate property schema is included in the Property Schemas List at the top of the **Property Fields** tab. If necessary, use the folder button to select the appropriate property schema by using the **BizTalk Type Picker** dialog box.</span></span> <span data-ttu-id="91135-110">次を選択します ダイアログ ボックスの左側にあるスキーマ ツリー内のノードを展開し、**フィールド要素**ノードまたは**フィールド属性**プロパティ フィールドとして昇格をクリックするノード**追加**します。</span><span class="sxs-lookup"><span data-stu-id="91135-110">Next, expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a property field, and then click **Add**.</span></span> <span data-ttu-id="91135-111">ドロップダウン リストの最後に、使用、**プロパティ**の列、**プロパティ フィールド ディクショナリ**を選択するテーブルを**フィールド要素**に使用するプロパティ スキーマのノード昇格させたプロパティに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="91135-111">Finally, use the drop-down list in the **Property** column of the **Property-Fields dictionary** table to select a **Field Element** node in a property schema with which to associate the promoted property.</span></span> <span data-ttu-id="91135-112">使用して、プロパティ フィールドにプロパティを昇格させる方法についてステップ バイ ステップの手順について、**プロパティの昇格** ダイアログ ボックスを参照してください[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。</span><span class="sxs-lookup"><span data-stu-id="91135-112">For step-by-step instructions about promoting properties to property fields using the **Promote Properties** dialog ox, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91135-113">昇格することも、**レコード**にノードを**フィールド要素**ノード プロパティのスキーマが場合にのみ、**コンテンツの種類**のプロパティ、**レコード**にノードが設定されている**SimpleContent**します。</span><span class="sxs-lookup"><span data-stu-id="91135-113">You can also promote a **Record** node to a **Field Element** node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91135-114">同じプロパティ昇格できます何度もスキーマ内でとして異なるルート ノードでこれらの昇格をすべて実行されます。</span><span class="sxs-lookup"><span data-stu-id="91135-114">The same property can be promoted multiple times within a schema as long as all of these promotions are performed under different root nodes.</span></span> <span data-ttu-id="91135-115">メッセージは単一のルート ノードに対して検証し、そのルート ノードで昇格したプロパティだけが実行時に評価されるためです。</span><span class="sxs-lookup"><span data-stu-id="91135-115">This is because the message is validated against a single root node and only properties promoted under that root node are evaluated at run time.</span></span>  
  
 <span data-ttu-id="91135-116">削除する、**フィールド要素**ノードまたは**フィールド属性**プロパティ フィールドとして昇格されるプロパティのセットからのノードで昇格させたプロパティを選択する、**プロパティ フィールド ディクショナリ**テーブルに対して、**プロパティ フィールド**タブをクリックし、をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="91135-116">To remove a **Field Element** node or **Field Attribute** node from the set of properties being promoted as property fields, select the promoted property in the **Property-Fields dictionary** table on the **Property Fields** tab, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="91135-117">**ノード パス**内の列、**プロパティ フィールド ディクショナリ**テーブルは、昇格させたプロパティに対応するスキーマ ノードの XPath を示します。</span><span class="sxs-lookup"><span data-stu-id="91135-117">The **Node Path** column in the **Property-Fields dictionary** table shows the XPath to the schema node corresponding to the promoted property.</span></span> <span data-ttu-id="91135-118">この値を使用して直接編集することができます、**インスタンス XPath の編集** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="91135-118">You can edit this value directly by using the **Edit Instance XPath** dialog box.</span></span> <span data-ttu-id="91135-119">省略記号をクリックして、このダイアログ ボックスを開くことができます (**.**) そのセルを選択すると、対応するセルの右端に表示されるボタン。</span><span class="sxs-lookup"><span data-stu-id="91135-119">You can open this dialog box by clicking the ellipsis (**...**) button that appears at the right end of the corresponding cell when you select that cell.</span></span> <span data-ttu-id="91135-120">BizTalk エディターで解決できない Xpath が適切な検証操作を防ぐために、XPath の値を直接編集するとき、十分に注意してする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91135-120">Care must be taken when editing XPath values directly because XPaths that cannot be resolved by BizTalk Editor will prevent proper validation operations.</span></span>  
  
 <span data-ttu-id="91135-121">BizTalk エディターを使用してプロパティを昇格できる便利なコマンドも提供します、**プロパティ フィールド**メカニズム。</span><span class="sxs-lookup"><span data-stu-id="91135-121">BizTalk Editor also provides a streamlined command for promoting properties using the **Property Field** mechanism.</span></span> <span data-ttu-id="91135-122">このコマンドはクイック昇格と呼ばれ、使用して設定できることをお勧めします **昇格と &#124; 文字です。クイック昇格** コマンド、BizTalk メニューとショートカット メニューをします。</span><span class="sxs-lookup"><span data-stu-id="91135-122">This command is called Quick Promotion, and it is available using the **Promote &#124; Quick Promotion** command on the BizTalk and shortcut menus.</span></span> <span data-ttu-id="91135-123">このコマンドは、選択した昇格**フィールド**ノード (または**レコード**ノード) で指定されたプロパティ スキーマが自動的に作成されるプロパティ フィールドに、**既定のプロパティ スキーマ名**プロパティ、**プロパティ ページ**含んでいるスキーマのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="91135-123">This command promotes the selected **Field** node (or **Record** node) to a property field that is automatically created in the property schema specified by the **Default Property Schema Name** property in the **Property Pages** dialog box for the containing schema.</span></span> <span data-ttu-id="91135-124">クイック昇格コマンドを使用して、プロパティ フィールドにプロパティを昇格させる方法についてステップ バイ ステップの手順については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。</span><span class="sxs-lookup"><span data-stu-id="91135-124">For step-by-step instructions about promoting properties to property fields using the Quick Promotion command, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="91135-125">プロパティ フィールドのメカニズムを使用してプロパティを昇格するときに、XML スキーマ定義 (XSD) 言語の 2 つのフラグメントは、メッセージ スキーマの XSD 表記に追加されます。</span><span class="sxs-lookup"><span data-stu-id="91135-125">When you promote a property by using the property field mechanism, two XML Schema definition (XSD) language fragments are added to the XSD representation of the message schema.</span></span> <span data-ttu-id="91135-126">最初の XSD フラグメントは、関連付けられる注釈フラグメント、**スキーマ**要素を次の例のように、対応するプロパティ スキーマを識別します。</span><span class="sxs-lookup"><span data-stu-id="91135-126">The first XSD fragment is an annotation fragment associated with the **schema** element that identifies the corresponding property schema, as in the following example:</span></span>  
  
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
  
 <span data-ttu-id="91135-127">2 番目の XSD フラグメントは、関連付けられる注釈フラグメント、**ルート**(かどうかが変更されています) に関係なく要素を識別する、**フィールド要素**ノードまたは**フィールド属性**プロパティを使用して昇格されたノードの値フィールドのメカニズムは、次の例のように。</span><span class="sxs-lookup"><span data-stu-id="91135-127">The second XSD fragment is an annotation fragment associated with the **Root** element (regardless of whether it has been renamed) that identifies the **Field Element** node or **Field Attribute** node values that have been promoted by using the property field mechanism, as in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91135-128">参照</span><span class="sxs-lookup"><span data-stu-id="91135-128">See Also</span></span>  
 <span data-ttu-id="91135-129">[メッセージの内容をコントロール メッセージの処理を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="91135-129">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="91135-130">プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="91135-130">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)