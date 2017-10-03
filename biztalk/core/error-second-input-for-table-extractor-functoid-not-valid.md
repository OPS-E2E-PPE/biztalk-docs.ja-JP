---
title: "エラー - の 2 番目の入力テーブル抽出 Functoid 有効 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970c0bfa23cc7da33b2c041cc326987ec278e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>エラー - の 2 番目の入力テーブル抽出 Functoid 有効
**エラー コード**  
  
 btm1073  
  
 **説明**  
  
 2 番目の入力パラメーターを関連する**テーブル抽出**functoid が有効ではありません。 このパラメーターは、テーブル ループ グリッドの構成で有効な列を示す正の整数定数である必要があります、**テーブル ループ**最初の入力パラメーターで示されている functoid です。  
  
 **ユーザーの操作**  
  
 関連するへの入力パラメーターを確認してください**テーブル抽出**functoid を使用してアクセスその**入力パラメーター**プロパティおよび**構成\<Functoid >Functoid**  ダイアログ ボックスでは、次の表に示すようにします。  
  
|テーブル抽出 Functoid の入力パラメーター番号|Description|  
|-----------------------------------------------------|-----------------|  
|1|リンク、**テーブル ループ**この functoid**テーブル抽出**functoid は、2 番目のパラメーターによって示される列のデータをプルします。|  
|2|構成データ テーブル内の有効な列の数、**テーブル ループ グリッド**のプロパティ、**テーブル ループ**functoid の最初の入力パラメーターで指定します。|