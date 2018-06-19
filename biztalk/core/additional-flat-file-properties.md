---
title: 追加のフラット ファイル プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c88ad2f-b5a8-46e6-b1b8-61ce6ba910d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9989d29eadf2487b84e2520755e879cd201b1798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230042"
---
# <a name="additional-flat-file-properties"></a>追加のフラット ファイル プロパティ

## <a name="hidden-properties"></a>非表示のプロパティ
次の表は、スキーマ エディターに表示されない追加のフラット ファイル ノード プロパティを示しています。 これらのプロパティを使用するには、テキスト エディターでスキーマ ファイルを編集する必要があります。  
  
|プロパティ|値|既定値|Description|  
|--------------|------------|-------------------|-----------------|  
|suppress_empty_nodes|**true** または **false**|**オプション**|パーサーが XML インスタンス データを生成した後に空の XML ノードを削除するかどうかを示します。|  
|generate_empty_nodes|**true** または **false**|**true**|XML インスタンス データに存在するレコードの空のノードを生成します。|  
|parser_optimization|**速度**または**複雑さ**|**速度**|速度の最適化を行うと、解析時間が短縮されます。ただし、データのあいまいさの処理が犠牲になります。 複雑さの最適化を行うと、幅広いあいまいさが処理されます。ただし、処理速度が犠牲になります。|  
|lookahead_depth|正の整数。ゼロ (0) は無制限の先読みを示します。|3|データ照合の先読みの程度を示します。|  
|allow_early_termination|**true** または **false**|**オプション**|位置指定レコードを早期終了するかどうかを示します (**true**) か、すべてのレコード フィールドのデータを含んでいる必要があります (**false**)。|  
|early_terminate_optional_fields|**true** または **false**|**オプション**|省略可能な後続のフィールドの早期終了を有効にする (**true**)。 既定値に設定してこの注釈を追加、この注釈のない既存のスキーマは、BizTalk エディターで開かれている場合、(**false**)。 **注:** early_terminate_optional_fields 注釈のみ有効になります、allow_early_termination が設定されている場合を"true"にします。|  
  
 属性は、これらすべてのプロパティ、 **/annotation/appinfo/schemaInfo**要素。  
  
 ときに**parser_optimization**に設定されている**複雑さ**、同じグループまたはレコード内の多くの省略可能なノードがある場合、スキーマに対して検証が失敗する必要があります。 設定する必要があります**lookahead_depth**検証エラーを回避するゼロ (0) にします。  
  
## <a name="see-also"></a>参照  
-  [ノードのプロパティ](../core/node-properties.md)   
-  **補足のノード プロパティのフラット ファイル スキーマ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]