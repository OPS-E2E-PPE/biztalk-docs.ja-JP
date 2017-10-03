---
title: "[メッセージ カウント] データベースの制限のしきい値に含まれる保留メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f8ea0643ccf2d6206ba86bc56b5dd54c0d51115
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a>[データベースのメッセージ カウント] の制限のしきい値に含まれる保留メッセージ
既定では、ホスト**DB 内の数をメッセージ**は、次の状況で制限の条件をトリガーする 50,000 値に設定されている制限のしきい値。  
  
-   サブスクライブを行うホストの作業キュー、状態キュー、および保留キューに対しこのホスト インスタンスによって公開されるメッセージの総数が、50,000 を超えた場合  
  
-   スプール テーブルまたは追跡テーブル内のメッセージの数は、500,000 メッセージを超えています。  
  
 保留中のメッセージが含まれているため、 **DB 内の数をメッセージ**計算、発行は、BizTalk server が低発生している場合でも発生する可能性がメッセージまたは負荷がまったくないを調整します。  
  
## <a name="recommendations"></a>推奨事項  
  
-   保留メッセージの数が多いがありますが予想される場合は、既定値を増やすことを検討、 **DB 内の数をメッセージ**しきい値を含む SQL server の容量の要件を考慮に入れて、BizTalk データベース。 増やすことを検討、**スプール乗数**と**追跡データ乗数**値が、スプール テーブルの追加のバックログを使用します。  
  
     これらの値の詳細については、次を参照してください。[リソース ベースの調整設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)です。  
  
-   使用して、**メッセージ公開の制限の状態**に関連付けられているパフォーマンス モニター カウンター **BizTalk:MessageAgent**現在の制限の状態を測定するパフォーマンス オブジェクト カテゴリ。 このカウンターの値が 6 に戻る場合は、中断されたインスタンスを確認し、必要に応じてそのインスタンスを終了または再開します。  
  
     ホスト制限パフォーマンス カウンターの詳細については、次を参照してください。[ホスト制限パフォーマンス カウンター](../core/host-throttling-performance-counters.md)です。  
  
## <a name="see-also"></a>参照  
 [設計の推奨事項の調整](../core/throttling-design-recommendations.md)