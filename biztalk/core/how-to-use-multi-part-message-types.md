---
title: "マルチパート メッセージの種類を使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87f210c4b0d2969edc9ddfa27b1d8494310eb6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-multi-part-message-types"></a>マルチパート メッセージの種類を使用する方法
各メッセージには、マルチパート メッセージの種類、0 個以上のメッセージ部分で構成されるメッセージ構造の記述があります。 これらの部分は、XSD (XML Schema Definition) 言語スキーマまたは .NET クラスによって定義されます。 独自のマルチパート メッセージの種類を定義したり、既存の .NET クラスおよびスキーマを使用することもできます。  
  
 メッセージ部分は、オーケストレーション内で直接アクセスしたり割り当てたりできます。また、識別フィールドまたはプロパティ フィールドとして公開されている、メッセージ部分の各要素を使用することもできます。 詳細については、次を参照してください。[識別フィールドおよびメッセージ プロパティ](../core/using-distinguished-fields-and-property-fields.md)です。  
  
> [!NOTE]
>  マルチパート メッセージの種類に含める部分は、複数とは限りません。  
  
> [!NOTE]
>  .NET の型によってメッセージ部分を定義することができます**XmlDocument**を任意の XML ドキュメントを含めるために使用できるし、.NET のある型を XML にシリアル化できる、またはいずれかで .NET カスタム シリアル化をサポートします。  
  
## <a name="add-a-multi-part-message-type"></a>マルチパート メッセージの種類を追加します。  
  
1.  **オーケストレーション**ウィンドウで、展開、**型**ノード。  
  
2.  右クリック**マルチパート メッセージの種類** をクリックし、**新しいマルチパート メッセージの種類**です。  
  
     **マルチパート メッセージの種類**が折りたたまれている場合、フォルダーを展開し、1 つの既定のメッセージ部分と共に新しいマルチパート メッセージの種類が追加されます。  
  
3.  マルチパート メッセージの種類、および提供されたメッセージ部分に名前を付けます。  
  
     名前を割り当てることによって他のパーツを追加するには、マルチパート メッセージの種類は、1 つ以上のメッセージ部分を必要とする場合、\<新規 > メッセージ部分です。  
  
4.  各メッセージ部分と、.NET クラスまたはスキーマなどの種類を関連付けます。  
  
## <a name="remove-a-multi-part-message-type"></a>マルチパート メッセージの種類を削除します。  
  
-   **オーケストレーション**ウィンドウで、右クリックして、マルチパート メッセージの種類を削除し、をクリックする**削除**です。  
  
    > [!NOTE]
    >  オーケストレーションからマルチパート メッセージの種類を削除すると、これが使用されているメッセージからも種類の情報が削除されます。  
  
    > [!NOTE]
    >  読み取り専用として表示される項目は、別のオーケストレーションで定義されています。  
  
## <a name="remove-a-part-from-a-multi-part-message-type"></a>マルチパート メッセージの種類から、一部を削除します。  
  
-   **オーケストレーションの種類**ウィンドウで、をクリックして削除する部分を右クリックして**削除**です。  
  
    > [!NOTE]
    >  場合は、メッセージの種類のメッセージ部分を削除することはできません、**メッセージのボディ部**プロパティが true に設定します。 最初に設定する必要があります、**メッセージのボディ部**プロパティをメッセージの種類の部分の別の True です。  
  
## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a>マルチパート メッセージの種類に対する型修飾子を設定します。  
  
-   **プロパティ**ウィンドウでは、次のプロパティを設定します。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |**型修飾子**|マルチパート メッセージの種類のスコープを設定します。<br /><br /> -   **Private-**マルチパート メッセージの種類へのアクセスが含まれているモジュールに制限されます。<br />-   **[パブリック]:**マルチパート メッセージの種類へのアクセスは制限されません。<br />-   **内部 —**マルチパート メッセージの種類へのアクセスは、同じプロジェクト内のモジュールに制限されます。|  
  
## <a name="add-parts-to-an-existing-multi-part-message"></a>既存のマルチパート メッセージに部分を追加します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マルチパート XLANG メッセージに部分を追加できます。また、最初に宣言した部分の数より大きいインデックスによってメッセージ部分 (存在する場合) を参照することもできます。 この機能は、可変数の添付ファイルを含んだ SMTP メッセージを送信または受信する場合に便利です。 この機能は、次のように実装されます。  
  
-   プロジェクトからへの参照を追加**Microsoft.XLANGs.BaseTypes**です。  
  
-   変数を作成 (たとえば*xlangPart*) 型の**Microsoft.XLANGs.BaseTypes.XLANGMessage**です。  
  
-   呼び出す*xlangPart***です。AddPart(...)**式図形から適切な引数を使用します。  
  
    > [!NOTE]
    >  追加された部分は型**XmlDocument**を使用してカスタムの書式設定されたメッセージ部分を追加することはできませんので、 **AddPart()**メソッドです。  
  
> [!NOTE]
>  宣言された部分の数よりも大きい値を含むマルチパート メッセージを受信する場合、オーケストレーション エンジン読み取りの数の部分がありますが、メッセージに作成で宣言されたメッセージ部分の数に一致する部分の適切な部分の種類型と、コンストラクト**XmlDocument**残りの部分の部分です。  
  
## <a name="see-also"></a>参照  
 **IBaseMessage.AddPart メソッド (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)   
 [識別フィールドおよびプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md)   
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)