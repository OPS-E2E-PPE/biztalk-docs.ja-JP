---
title: エラー - の 2 番目の入力テーブル ループ Functoid が無効です |Microsoft Docs
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
ms.openlocfilehash: 24ab38e947667e894445399e1916fe9e0a3b26fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346917"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a>エラー - の 2 番目の入力テーブル ループ Functoid が無効です。
**エラー コード**  
  
 btm1072  
  
 **説明**  
  
 2 番目の入力パラメーターを関連する**テーブル ループ**functoid が無効です。 このパラメーターは、関連付けられているテーブル ループ グリッド内の列の数を示す正の整数である必要があります。  
  
 **ユーザーの操作**  
  
 入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ functoid の入力パラメーター番号|説明|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。|  
|3 – 100|定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。|