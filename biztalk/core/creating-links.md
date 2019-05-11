---
title: リンクの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441ae9536dec11f8eead5544e95b7ba7f7814852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353646"
---
# <a name="creating-links"></a>リンクを作成します。
BizTalk マッパーでは、リンクの作成に関連するいくつかの要素を自動化するのに役立ちます。 簡易リンク作成は、単純なデータ型に似ています。 プログラミング言語の構造の割り当てに似ているリンクの作成のより高度な形式はあります。 たとえば、入力インスタンス メッセージから対応する出力インスタンス メッセージに移動するデータの複数の項目を指定する 1 つのリンクの作成です。  
  
 次のメソッドを使用してリンクを作成します。  
  
-   **簡易リンク作成します。** 単純なリンクを作成するには、ドラッグしてリンクを生成します。 送信先スキーマ内のフィールドに、送信元スキーマ内のフィールドをドラッグするが作成され、要素または属性の出力インスタンス メッセージにし、メッセージの要素または属性の値を挿入します。 このようなリンクは間で直接行われたことができます**レコード**と**フィールド**、送信元と送信先スキーマ内のノード間のリンク パスで 1 つまたは複数の functoid を含めることができますか**レコード**と**フィールド**元と送信先スキーマ内のノード。  
  
-   **構造リンクを示します。** 構造リンクを作成するでの間で同時に複数の簡易リンクを生成する**レコード**と**フィールド**同じ相対構造を持つ元と送信先スキーマ内のノード。 構造リンクを使用するには、は、2 つのスキーマの関連する部分の構造は同じである必要があります。 構造リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)します。  
  
-   **名前の一致リンク。** 間で同時に複数の簡易リンクを作成するときに、このメソッドを使用すると、**レコード**と**フィールド**元と送信先スキーマのノードの名前に基づく、 **レコード**と**フィールド**ノード。 名前の一致リンクを使用する元と送信先スキーマの構造があります非常に似ていますが、まったく同じです。 名前の一致リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)します。  
  
    > [!NOTE]
    >  表示することも[既存のリンクを管理する方法](../core/how-to-manage-existing-links.md)既存のリンクを変更する方法についてはします。  
  
## <a name="preserving-whitespace-in-a-link"></a>リンクの空白の保持  
 ターゲット要素または functoid をマップするときに、ソース要素から空白を保持する場合は、カスタム スクリプトを記述する必要があります。  
  
 マッパーでまたはをランタイム システムでは、空白は保持されません。 マッパーとランタイム システムの両方は、サイズの大きいメッセージの変換を処理し、移動、XPath データ モデルを使用する XmlReader 依存 BTSXslTransform.Transform を使用します。  
  
 空白を保持するために必要な数の空白を返すカスタム スクリプトを記述できます。 たとえば、次のコードでは、常に 5 文字の空白を含む文字列を返します。  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 ソース要素にリンクしたこのスクリプトとターゲット要素の入力、出力としてマップを実行すると、出力要素は、5 文字の空白が含まれます。  
  
> [!NOTE]
>  使用して出力を表示する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]要素は空として表示されます。 これは、XML ビューアーは空として空白を含む要素を処理するためです。 空白を確認するには、XML ビューを右クリックして**ソースの表示**します。  
  
## <a name="see-also"></a>参照  
 [リンクのプロパティを編集する方法](../core/how-to-edit-link-properties.md)