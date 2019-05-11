---
title: エラー - の 2 番目の入力テーブル抽出 Functoid へ有効 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c53e84e62422a70214a4cfd90979de85538e158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388435"
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>エラー - の 2 番目の入力テーブル抽出 Functoid へ無効です
**エラー コード**  
  
 btm1073  
  
 **説明**  
  
 2 番目の入力パラメーターを関連する**テーブル抽出**functoid が無効です。 このパラメーターは、テーブル ループ グリッド用に構成された有効な列を示す正の整数定数である必要があります、**テーブル ループ**functoid の最初の入力パラメーターで示されます。  
  
 **ユーザーの操作**  
  
 入力パラメーターを関連することを確認**テーブル抽出**functoid を使用してアクセスその**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル抽出 functoid の入力パラメーター番号|説明|  
|-----------------------------------------------------|-----------------|  
|1|リンク、**テーブル ループ**元である functoid**テーブル抽出**functoid が 2 番目のパラメーターで示されている列のデータをプルします。|  
|2|使用して構成データのテーブルで有効な列の数、**テーブル ループ グリッド**のプロパティ、**テーブル ループ**functoid の最初の入力パラメーターで指定します。|