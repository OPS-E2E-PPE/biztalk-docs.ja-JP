---
title: エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a>エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません。
**エラー コード**  
  
 btm1077  
  
 **説明**  
  
 ほとんどの functoid とは異なり、**テーブル ループ**functoid が複数の出力。 これらの出力の 1 つを除くすべての環境は、個別のインスタンスに最初の入力パラメーターとして接続されている必要があります、**テーブル抽出**functoid です。 残りの出力に接続されている必要があります、**レコード**送信先スキーマのノード (の適切な繰り返し設定)。 この後者の場合、このエラーが発生した出力リンクから、**テーブル ループ**functoid がありません。  
  
 **ユーザーの操作**  
  
 指定したドラッグ**テーブル ループ**を適切なレコード**レコード**不足しているリンクを作成する送信先スキーマのノードです。