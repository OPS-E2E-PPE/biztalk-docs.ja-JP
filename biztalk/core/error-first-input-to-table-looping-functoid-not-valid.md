---
title: エラー - テーブル ループ Functoid の無効への最初の入力 |Microsoft Docs
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
ms.openlocfilehash: 20ecfb5402cc4c544acc208654cd7fe7459de985
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389296"
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>エラー - テーブル ループ Functoid の無効への最初の入力
**エラー コード**  
  
 btm1071  
  
 **説明**  
  
 最初の入力パラメーターに関連する**テーブル ループ**functoid が無効です。 このパラメーターは、送信元スキーマのノードからのリンクである必要があります-入力インスタンス メッセージ内の対応する要素の出現回数が関連付けられている、一連の回数を制御**テーブル抽出**functoid実行時に呼び出されます。  
  
 **ユーザーの操作**  
  
 入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル ループ functoid の入力パラメーター番号|説明|  
|---------------------------------------------------|-----------------|  
|1|入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。|  
|2|使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。|  
|3 – 100|定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。|