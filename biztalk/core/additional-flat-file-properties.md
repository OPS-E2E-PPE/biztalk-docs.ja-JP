---
title: 追加のフラット ファイル プロパティ |Microsoft Docs
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
ms.openlocfilehash: cab0391fd8ffb8388d113301f7a3655f703c2c77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360731"
---
# <a name="additional-flat-file-properties"></a>追加のフラット ファイル プロパティ

## <a name="hidden-properties"></a>非表示のプロパティ
次の表は、スキーマ エディターで表示されていない追加のフラット ファイル ノードのプロパティを一覧表示します。 これらのプロパティを使用するには、手の形、テキスト エディターでスキーマ ファイルを編集する必要があります。  

|プロパティ|値|既定値|説明|  
|--------------|------------|-------------------|-----------------|  
|suppress_empty_nodes|**true** または **false**|**false**|パーサーが XML インスタンス データを生成した後は、空の XML ノードを削除するかどうかを示します。|  
|generate_empty_nodes|**true** または **false**|**true**|XML インスタンス データに存在するレコードの空のノードを生成します。|  
|parser_optimization|**速度**または**複雑さ**|**速度**|速度の低下、解析時間ですが処理するデータのあいまいさを犠牲を最適化します。 複雑さの最適化は、あいまいさの処理速度しますが、より広い範囲を処理します。|  
|lookahead_depth|正の整数。ゼロ (0) では、無制限の先読みを示します。|3|先読みしてデータを照合するまでにする方法。|  
|allow_early_termination|**true** または **false**|**false**|位置指定レコードを早期に終了するかどうかを示します (**true**) またはすべてのレコード フィールドのデータを格納する必要があります (**false**)。|  
|early_terminate_optional_fields|**true** または **false**|**false**|末尾の省略可能なフィールドの早期終了を有効にする (**true**)。 既定値に設定してこの注釈を追加、この注釈のない既存のスキーマが BizTalk エディターで開かれる場合 (**false**)。 **注:** Early_terminate_optional_fields 注釈は、allow_early_termination が設定されている場合のみ効果を与える"true"にします。|  

 これらのプロパティのすべての属性は、 **/annotation/appinfo/schemaInfo**要素。  

 ときに**parser_optimization**に設定されている**複雑さ**、同じグループまたはレコードの省略可能な多くのノードがある場合は、スキーマに対して検証が失敗する必要があります。 設定する必要があります**lookahead_depth**検証エラーを回避するためにゼロ (0) にします。  

## <a name="see-also"></a>参照  
- [ノードのプロパティ](../core/node-properties.md)   
- **フラット ファイル スキーマの補足のノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
