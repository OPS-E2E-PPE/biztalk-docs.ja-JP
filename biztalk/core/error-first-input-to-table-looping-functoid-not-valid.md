---
title: エラー - テーブル ループ Functoid が有効でないへの最初の入力 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9ebecbd92b43dd25e6ff3dde04d942b936f40d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968336"
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>エラー - テーブル ループ Functoid が有効でないへの最初の入力
**エラー コード**  
  
 btm1071  
  
 **説明**  
  
 関連する最初の入力パラメーター**テーブル ループ**functoid が有効ではありません。 このパラメーターは、送信元スキーマ内のノードからのリンクを指定する必要があります: 入力インスタンス メッセージ内の対応する要素の出現回数が関連付けられている一連の回数を制御する**テーブル抽出**functoid実行時に呼び出されます。  
  
 **ユーザーの操作**  
  
 入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ Functoid の入力パラメーター番号|Description|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。|  
|3 – 100|テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。|