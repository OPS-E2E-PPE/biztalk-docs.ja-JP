---
title: メジャーを定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 536ed57c16d135153765ad1f0d8b3a208106b8b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004123"
---
# <a name="how-to-define-measures"></a>メジャーを定義する方法
メジャーでは、アクティビティの計算方法を定義します。 BAM ビューの作成時、ビューのアクティビティにメジャーを定義できます。 たとえば、発注アクティビティの場合は、PO の合計金額、PO の数、PO の平均金額などを計算できます。  
  
 BAM では次のメジャーがサポートされています。  
  
-   SUM  
  
-   Count  
  
-   平均  
  
-   最小  
  
-   [最大]  
  
> [!NOTE]
>  現在のところ、BAM のリアルタイム集計 (RTA) 機能では、最小値メジャーと最大値メジャーはサポートされていません。 これらのメジャーを使用することはできますが、Excel のピボットテーブルを RTA としてマークしたとき、最小値と最大値は無視されます。  
  
### <a name="to-add-new-measures"></a>新しいメジャーを追加するには  
  
1. BAM ビュー ウィザードで、**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。 クリックして**新しいメジャー**します。  
  
2. メジャーの名前を入力します。  
  
3. ドロップダウン リストから、選択、**基本データ項目**します。  
  
4. をクリックして、**集計の種類**を使用します。 選択肢は次のとおりです。  
  
   -   SUM  
  
   -   Count  
  
   -   平均  
  
   -   最小 (rta はサポートされていません)。  
  
   -   最大値 (RTA では未サポート)  
  
5. **[OK]** をクリックします。 ディメンションとメジャーの追加が完了したら、クリックして**次**します。  
  
6. **新しい BAM ビュー: 概要** ページで、新しいビューに関する情報を確認してをクリックし、**次**。  
  
7. クリックして**完了**を完了する、 **BAM ビュー ウィザード**します。  
  
   BAM ビューにメジャーとディメンションを追加したら、これらの項目を Excel ブックのピボットテーブルに追加できます。 ピボット テーブルの作成の詳細については、次を参照してください。[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)します。  
  
## <a name="see-also"></a>参照  
 [ディメンションの定義](../core/defining-dimensions.md)