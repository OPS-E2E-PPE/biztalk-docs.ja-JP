---
title: "エラー - テーブル ループ Functoid が有効でないへの最初の入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2cfa89175d566ed152caa852dfc7aef2b435447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>エラー - テーブル ループ Functoid が有効でないへの最初の入力
**エラー コード**  
  
 btm1071  
  
 **説明**  
  
 関連する最初の入力パラメーター**テーブル ループ**functoid が有効ではありません。 このパラメーターは、送信元スキーマ内のノードからのリンクを指定する必要があります: 入力インスタンス メッセージ内の対応する要素の出現回数が関連付けられている一連の回数を制御する**テーブル抽出**functoid実行時に呼び出されます。  
  
 **ユーザーの操作**  
  
 入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid > Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ Functoid の入力パラメーター番号|Description|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。|  
|3 – 100|テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。|