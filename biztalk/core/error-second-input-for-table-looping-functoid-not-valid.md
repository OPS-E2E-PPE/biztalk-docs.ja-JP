---
title: エラー - の 2 番目の入力テーブル ループ Functoid は無効です |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb321a26300a514357225713db1b197fb828851
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970264"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a>エラー - の 2 番目の入力テーブル ループ Functoid は無効です。
**エラー コード**  
  
 btm1072  
  
 **説明**  
  
 2 番目の入力パラメーターを関連する**テーブル ループ**functoid が有効ではありません。 このパラメーターは、関連付けられているテーブル ループ グリッドの列数を示す正の整数である必要があります。  
  
 **ユーザーの操作**  
  
 入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ Functoid の入力パラメーター番号|Description|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。|  
|3 – 100|テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。|