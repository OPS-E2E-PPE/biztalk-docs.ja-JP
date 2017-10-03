---
title: "発効日プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="effective-date-properties"></a>発効日のプロパティ
PeopleSoft Enterprise には、Effective Date (省略表記 EFFDT) と呼ばれる特殊なプロパティを使用して、計画済み項目のスケジュール作成と追跡を行う機能があります。 計画済み項目は、日付が PeopleSoft の現在の日付よりも前か後かによって、既に有効になっている項目であるか、単に計画されているだけの項目であるかが決定します。  
  
 コンポーネント インターフェイスのプロパティに、発効日が指定された項目 (つまり、EFFDT という名前のフィールド) が含まれている場合、呼び出し元はアダプターを介して、値の完全なセットを取得するか、まだ有効になっていない (まだ変更可能な) 値だけを取得できます。  
  
## <a name="gethistoryitems-parameter"></a>getHistoryItems パラメーター  
 発効日を含むプロパティを持つコンポーネント インターフェイスには、Get 操作用の `getHistoryItems` という追加のパラメーターがアダプターによって提供されます。 このパラメーターはブール値型であり、True に設定されています (つまり、発効日が指定されたすべての項目が返されます)。 返されるのは、過去、現在、および将来の発効日が指定されたすべての項目です。  
  
 `getHistoryItems` パラメーターが False に設定されている場合は、現在および将来の発効日が指定された項目のみが返されます。 そのような項目を追加または変更する場合に、False を選択します (過去の項目は変更できません)。  
  
 また、複数の項目に同じ発効日が指定されている場合があります。 この場合は、追加のプロパティとして Effective Sequence (EFFSEQ) も指定する必要があります。 同じ発効日を持つ複数の項目を区別するために、EFFSEQ の値は一意である必要があります。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
## <a name="modifying-past-effective-dated-items"></a>過去の発効日が指定された項目の変更  
 `correctionMode`両方の引数、 [UpdateEx](../core/updateex-method.md)と[DeleteOnly](../core/deleteonly-method.md)メソッドは、過去の有効日が指定された項目を変更できるかどうかを制御します。 true に設定されている場合は、すべての項目を変更できます。 それ以外の場合、過去の発効日が指定された項目を変更すると例外が生成されます。  
  
 発効日が指定された項目を含むコンポーネント インターフェイスに対して、廃止された `Update` メソッドを呼び出す場合は、PeopleSoft の現在の日付よりも前の値を持つ発効日を対象に含めないように注意する必要があります。これに従わない場合は、例外が発生して呼び出しが失敗します。 ただし、発効日として現在の日付が指定された項目は、プロパティ設定時にバイパスされるので、含めてかまいません。 Effective Sequence が設定されている場合、発効日として現在の日付が指定された項目のうち、サーバーの Effective Sequence に一致するすべての項目が、プロパティ設定時にスキップされます。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)