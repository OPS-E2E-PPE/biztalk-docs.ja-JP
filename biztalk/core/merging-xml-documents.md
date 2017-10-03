---
title: "XML ドキュメントのマージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94684cd9bf1992a592efd7b97c46838c9c9a3134
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="merging-xml-documents"></a>XML ドキュメントのマージ
いずれかのメッセージを**OrderBroker**オーケストレーションを作成、SQL Server 履歴データベースを更新する 1 つです。 このメッセージには、元の注文メッセージと注文メッセージのフィールドが含まれます。 元の注文は、このメッセージに文字列として表示されます。 これは、データベースの注文履歴のデータ型と一致します。  
  
 メッセージを取得し、文字列に変換して、マップと一緒に別のメッセージに配置することはできません。 オーケストレーションで使用するヘルパー関数**InsertOrderBody**、元の注文メッセージを文字列としてベースの履歴メッセージに追加します。  
  
 **OrderBroker**オーケストレーションは、マップを使用して**CSR_OrderRequest_To_SQLHistoryInsert**、注文メッセージ ベースの履歴メッセージに変換します。 属性として、注文の情報が表示されます、 **OrderLog**要素。 元のメッセージは、この要素の別の属性として表示されます。  
  
 **InsertOrderBody**メソッド引数として、元の注文メッセージ ベースの履歴メッセージを受け取り、完成された履歴メッセージを返します。 次のコードは、文字列としてメッセージを挿入するメソッドの一部を示しています。  
  
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
  
 両方の引数が受信したことを確認した後、 **InsertOrderBody**メソッドは、履歴更新メッセージのルート ノードを検索します。 これは、後、作成、ノードを含む、 **OriginalMsg**属性し、属性の値を元の注文メッセージを割り当てます。 この時点では、ノードは単に存在しているだけです。 ノードは、まだ要素の一部ではありません。  
  
 属性ノードを作成すると、このメソッドは、XPath 式で属性を追加するノードを検索します。 ノードを検出すると、このメソッドは、ノードの Attributes コレクションに属性ノードを追加します。  
  
> [!NOTE]
>  ただし、 **OriginalMsg**属性は、ベースの履歴メッセージに最初に存在しません、これは、もちろん、スキーマで指定します。 コードでメッセージに追加する XML 要素は、そのメッセージ用のスキーマで指定する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)