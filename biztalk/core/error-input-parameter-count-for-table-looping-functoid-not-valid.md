---
title: エラー - テーブル ループ Functoid が無効の入力パラメーター数が |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df0a6780485b91fc89356aecb73823643276be1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968464"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a>エラー - テーブル ループ Functoid が無効の入力パラメーター数
**エラー コード**  
  
 btm1070  
  
 **説明**  
  
 関連する指定された入力パラメーター数**テーブル ループ**functoid が有効ではありません。  
  
 **ユーザーの操作**  
  
 入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ Functoid の入力パラメーター番号|Description|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。|  
|3 – 100|テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。|