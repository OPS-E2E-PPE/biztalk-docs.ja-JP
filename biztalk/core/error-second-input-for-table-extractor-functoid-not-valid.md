---
title: エラー - の 2 番目の入力テーブル抽出 Functoid 有効 |Microsoft ドキュメント
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
ms.openlocfilehash: 5e674ad6777ebff53fefe053e1b6af46ebc54ef3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970680"
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>エラー - の 2 番目の入力テーブル抽出 Functoid 有効
**エラー コード**  
  
 btm1073  
  
 **説明**  
  
 2 番目の入力パラメーターを関連する**テーブル抽出**functoid が有効ではありません。 このパラメーターは、テーブル ループ グリッドの構成で有効な列を示す正の整数定数である必要があります、**テーブル ループ**最初の入力パラメーターで示されている functoid です。  
  
 **ユーザーの操作**  
  
 関連するへの入力パラメーターを確認してください**テーブル抽出**functoid を使用してアクセスその**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル抽出 Functoid の入力パラメーター番号|Description|  
|-----------------------------------------------------|-----------------|  
|1|リンク、**テーブル ループ**この functoid**テーブル抽出**functoid は、2 番目のパラメーターによって示される列のデータをプルします。|  
|2|構成データ テーブル内の有効な列の数、**テーブル ループ グリッド**のプロパティ、**テーブル ループ**functoid の最初の入力パラメーターで指定します。|