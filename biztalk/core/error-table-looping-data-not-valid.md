---
title: エラー - テーブル ループ データが有効ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9478026980ecaf3e2049773737250c56d18262c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968539"
---
# <a name="error---table-looping-data-not-valid"></a>エラー - テーブル ループ データが有効ではありません。
**エラー コード**  
  
 btm1065  
  
 **説明**  
  
 関連する関連付けられたデータのテーブル**テーブル ループ**functoid が正しくない可能性があります、functoid、または正しく構成されていない、テーブル ループ グリッドを 2 番目の入力パラメーターが正しく構成されているためです。  
  
 **ユーザーの操作**  
  
 入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ Functoid の入力パラメーター番号|Description|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。|  
|3 – 100|テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。|  
  
 また、[を介してアクセスされると、テーブル ループ グリッドを正しく構成することを確認してください、**テーブル ループ グリッド**プロパティおよび**テーブル ループの構成**] ダイアログ ボックス。 アクセスされるすべてのセルの定数またはリンク値を選択する必要があります、関連付け**テーブル抽出**functoid です。