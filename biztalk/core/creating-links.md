---
title: "リンクを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-links"></a>リンクを作成します。
BizTalk マッパーを使用すると、リンク作成に関連する一部の要素を自動化できます。 簡易リンク作成は、単純なデータ型に似ています。 プログラミング言語の構造の割り当てに似ている高度な形式のリンク作成もあります。 たとえば、入力インスタンス メッセージから対応する出力インスタンス メッセージに複数の項目のデータを移動する方法を指定するリンク作成などがあります。  
  
 次の方法で、リンクを作成します。  
  
-   **簡易リンク作成します。** 簡易リンクを作成するには、ドラッグ操作でリンクを作成します。 送信元スキーマのフィールドを送信先スキーマのフィールドにドラッグすると、出力インスタンス メッセージの要素または属性が作成され、要素または属性の値がメッセージに挿入されます。 このようなリンクにできる間で直接**レコード**と**フィールド**、送信元と送信先スキーマのノード間のリンク パスに 1 つまたは複数の functoid を含めることができます、または**レコード**と**フィールド**送信元と送信先スキーマのノードです。  
  
-   **構造リンクを示します。** 構造リンクを作成するには、間で同時に複数の簡易リンクを生成する**レコード**と**フィールド**同じ相対構造を持つ送信元と送信先スキーマのノードです。 構造リンクを使用するには、2 つのスキーマの関連する部分の構造が同じであることが必要です。 構造リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。  
  
-   **名前の一致リンク。** 間で同時に複数の簡易リンクを作成するときに、このメソッドを使用する**レコード**と**フィールド**の名前に基づいて、送信元と送信先スキーマのノード、**レコード**と**フィールド**ノード。 名前の一致リンクを使用するには、送信元スキーマおよび送信先スキーマの構造が非常に似ている (ただし、完全に同じではない) 必要があります。 名前の一致リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。  
  
    > [!NOTE]
    >  表示することも[既存のリンクを管理する方法](../core/how-to-manage-existing-links.md)既存のリンクを変更または変更する方法についてはします。  
  
## <a name="preserving-whitespace-in-a-link"></a>リンクでの空白の保持  
 ソース要素からターゲット要素または Functoid にマッピングする際に、要素内の空白を保持する場合は、カスタム スクリプトを記述する必要があります。  
  
 マッパーとランタイム システムのいずれにおいても空白は保持されません。 マッパーとランタイム システムの両方が、サイズの大きいメッセージの変換に BTSXslTransform.Transform を使用し、ナビゲーション操作に XmlReader と XPath データ モデルを使用します。  
  
 空白を保持するには、必要な数の空白を返すカスタム スクリプトを記述できます。 たとえば、次のコードでは常に 5 文字の空白を含む文字列が返されます。  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 ソース要素をこのスクリプトの入力とし、ターゲット要素を出力としてリンクすると、マップの実行後、出力要素には 5 文字の空白が含められます。  
  
> [!NOTE]
>  使用して、出力を表示する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]要素は空として表示されます。 この理由は、XML ビューアーでは空白を含む要素は空として扱われるためです。 空白を確認するには、XML ビューを右クリックして**ソースの表示**です。  
  
## <a name="see-also"></a>参照  
 [リンクのプロパティを編集する方法](../core/how-to-edit-link-properties.md)