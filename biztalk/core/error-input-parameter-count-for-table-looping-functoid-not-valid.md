---
title: エラー - テーブル ループ functoid への無効の入力パラメーター数が |Microsoft Docs
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
ms.openlocfilehash: 68cc75282c7dd18925f39b339521d8ecb41911b9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530724"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a>エラー - テーブル ループ functoid への無効の入力パラメーター数
**エラー コード**  
  
 btm1070  
  
 **説明**  
  
 関連する指定された入力パラメーター数**テーブル ループ**functoid が無効です。  
  
 **ユーザーの操作**  
  
 入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ functoid の入力パラメーター番号|説明|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。|  
|3 – 100|定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。|