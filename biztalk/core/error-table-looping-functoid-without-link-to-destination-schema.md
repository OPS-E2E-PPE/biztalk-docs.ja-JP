---
title: エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません |Microsoft Docs
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
ms.openlocfilehash: ee53c8317b3b5d36c6856123354aab5746d5e84d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346606"
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a>エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません。
**エラー コード**  
  
 btm1077  
  
 **説明**  
  
 ほとんどの functoid とは異なり、**テーブル ループ**functoid が複数の出力。 これらの出力の 1 つを除くすべての個別のインスタンスへの最初の入力パラメーターとして接続する必要があります、**テーブル抽出**functoid。 残りの出力に接続する必要があります、**レコード**(適切な繰り返しの設定) で、送信先スキーマのノード。 このエラーは、この後者の場合に発生します。 出力リンクから、**テーブル ループ**functoid が見つかりません。  
  
 **ユーザーの操作**  
  
 指定したドラッグ**テーブル ループ**を適切なレコード**レコード**不足しているリンクを作成する送信先スキーマ内のノード。