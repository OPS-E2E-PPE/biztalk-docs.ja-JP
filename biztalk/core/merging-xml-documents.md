---
title: XML ドキュメントのマージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 442df8925a37089d7a5ae933dcc572947a161095
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394590"
---
# <a name="merging-xml-documents"></a>XML ドキュメントのマージ
メッセージのいずれかを**OrderBroker**オーケストレーションの作成は SQL Server 履歴データベースを更新する 1 つです。 このメッセージには、元の注文メッセージと同様に、注文メッセージのフィールドが含まれています。 元の順序では、文字列がこのメッセージに表示されます。 これは、データベース内の注文履歴のデータ型と一致します。  
  
 メッセージを取得、文字列に変換し、マップと一緒に別のメッセージ内に配置することはできません。 オーケストレーションで使用するヘルパー関数**InsertOrderBody**、元の注文メッセージを文字列としてベースの履歴メッセージに追加します。  
  
 **OrderBroker**オーケストレーションは、マップを使用して**CSR_OrderRequest_To_SQLHistoryInsert**、注文メッセージ ベースの履歴メッセージに変換します。 属性として、注文の情報が表示されます、 **OrderLog**要素。 この要素の別の属性として、元のメッセージが表示されます。  
  
 **InsertOrderBody**メソッド ベースの履歴メッセージでは、元の注文メッセージを引数として受け取り、完成された履歴メッセージを返します。 次のコードは、文字列としてメッセージを挿入するメソッドの一部を示しています。  
  
```  
public static XmlDocument InsertOrderBody( XmlDocument orderDoc,   
                                    XmlDocument historyInsertDoc)  
{  
...  
    XmlNode root = historyInsertDoc.FirstChild;  
  
    //Create a new attribute.  
    XmlNode attr = historyInsertDoc.CreateNode(XmlNodeType.Attribute,  
                                     "OriginalMsg", root.NamespaceURI);  
    attr.Value = orderDoc.OuterXml;  
  
    try  
    {  
        // XPath expression not shown for formatting reasons and  
        // replaces ".." in the following code  
        XmlNode destnode = historyInsertDoc.SelectSingleNode("..");  
        //Add the attribute to the document.  
        destnode.Attributes.SetNamedItem(attr);  
    }  
...  
  
    return historyInsertDoc;  
}  
```  
  
 両方の引数が受信したことを確認した後、 **InsertOrderBody**メソッドは、履歴更新メッセージのルート ノードを検索します。 これは、後、作成、ノードを含む、 **OriginalMsg**属性し、属性の値に元の注文メッセージを割り当てます。 この時点では、ノードが存在するだけです。 これはまだ要素の一部ではありません。  
  
 属性ノードを作成した後は、メソッドは、XPath 式を使用して属性をアタッチはノードを検索します。 ノードを検出した後、メソッドは、ノードの属性のコレクションに属性ノードを追加します。  
  
> [!NOTE]
>  ただし、 **OriginalMsg**属性は、ベースの履歴メッセージに最初に存在しません、これは、もちろん、スキーマで指定します。 コードでメッセージに追加する XML 要素は、これらのメッセージのスキーマで指定する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-business-process-management-solution.md)