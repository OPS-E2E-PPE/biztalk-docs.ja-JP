---
title: "日付と時刻 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec31607ecefb417fef597b5ba700e6461c71a2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="date-and-time-functoids"></a>日付と時刻 Functoid

## <a name="overview"></a>概要
**日付/時刻**functoid は 2 つのカテゴリに分けることができます。 最初のカテゴリには、1 つの functoid が含まれています。**日数加算**、を使用して、指定した日付と時刻の値を指定した日数を追加します。 これは、出力インスタンス メッセージのフィールドが将来の日時の推定値を含む場合に役立ちます。 たとえば、**日数加算**見積もりを生成する functoid を使用することができます、注文を受け取った日付からの固定の差分に基づいて出荷日。  
  
 2 番目のカテゴリには、すべての残りの functoid が含まれています、**日付と時刻**カテゴリ。 これらの Functoid を使用して実行時にタイムスタンプを提供することで、メッセージ変換が行われる日時を出力インスタンス メッセージに格納できます。  
  
 **日数加算**functoid が、2 つの入力パラメーターを受け入れる、**日付**、**日付と時刻**、および**時間**functoid に入力いるなしパラメーター。  

## <a name="available-functoids"></a>使用可能な functoid  
 **日付/時刻**functoid には。 

* 日数加算
* 日付
* 日時
* [時刻]

これらの functoid の詳細については、使用可能な**Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
-  [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **日時 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]