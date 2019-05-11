---
title: エラー - テーブル ループ データが無効です |Microsoft Docs
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
ms.openlocfilehash: e62678e7dc4e0aceee128cb24bc0ff34129168cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388407"
---
# <a name="error---table-looping-data-not-valid"></a>エラー - テーブル ループ データが無効です。
**エラー コード**  
  
 btm1065  
  
 **説明**  
  
 関連付けられた、関連するデータのテーブル**テーブル ループ**functoid が無効で、functoid、または正しく構成されていない、テーブル ループ グリッドを 2 番目の入力パラメーター構成が正しくない可能性があります。  
  
 **ユーザーの操作**  
  
 入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ functoid の入力パラメーター番号|説明|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。|  
|3 – 100|定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。|  
  
 またを正しくテーブル ループ グリッドを構成することを確認、**テーブル ループ グリッド**プロパティおよび**テーブル ループの構成** ダイアログ ボックス。 アクセスするすべてのセルの定数またはリンクの値を選択する必要が、関連付けられた**テーブル抽出**functoid。