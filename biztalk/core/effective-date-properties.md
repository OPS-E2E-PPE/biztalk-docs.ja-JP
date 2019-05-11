---
title: 発効日のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42373f55391f8bf3401d18e0a964005def222a8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389099"
---
# <a name="effective-date-properties"></a>発効日のプロパティ
PeopleSoft Enterprise では、スケジュールを設定し、計画済み項目有効日 (省略表記 EFFDT) と呼ばれる特殊なプロパティを使用しての追跡機能を提供します。 このような項目は有効か単予定、その日付が PeopleSoft の現在の日付の前後のかによってです。  
  
 コンポーネント インターフェイスのプロパティにこのような effective-dated 項目 (つまり、EFFDT の名前を持つフィールド) が含まれている場合、アダプターによって、呼び出し元の値または値のみの完全なセットに取得をまだ有効な変更することもできます.  
  
## <a name="gethistoryitems-parameter"></a>getHistoryItems パラメーター  
 発効日を含むプロパティを持つコンポーネント インターフェイスでは、アダプターと呼ばれる追加のパラメーターを提供します`getHistoryItems`、Get 操作をします。 このパラメーターは、Boolean 型とを True に設定されている場合、すべて、effective-dated 項目が返されます。 すべての過去、現在および将来の発効項目が含まれます。  
  
 場合、`getHistoryItems`パラメーターは、False に設定されて、現在および将来の発効項目のみが返されます。 追加または (過去のアイテムを変更できない) ために、これらの項目を変更する場合は False を選択します。  
  
 複数発効項目を同じ発効日を持つこともできます。 このような状況で効果的なシーケンス (EFFSEQ)、追加のプロパティを指定も必要があります。 EFFSEQ の値は、有効日が同じ項目を区別するために一意である必要があります。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
## <a name="modifying-past-effective-dated-items"></a>過去の発効日が指定された項目を変更します。  
 `correctionMode`両方の引数、 [UpdateEx](../core/updateex-method.md)と[DeleteOnly](../core/deleteonly-method.md)メソッドは、過去の有効日が指定された項目を変更できるかどうかを制御します。 設定されている場合は true、すべての項目変更できます。 それ以外の場合、有効日が指定された項目には、例外が生成されます。 過去の変更。  
  
 非推奨の呼び出し時に`Update`effective-dated 項目を含むコンポーネント インターフェイスのメソッドは、する必要がありますように注意する現在の有効な日付または呼び出しで例外で失敗 PeopleSoft より前の値の有効な日付を含める必要はありません。 ただし、発効の現在の項目を含めるようにプロパティを設定するときにバイパスされますができます。 Effective Sequence が存在する場合は、プロパティを設定するときに、すべて現在、effective-dated 項目が有効なシーケンスを一致するサーバーではスキップされます。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)