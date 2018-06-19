---
title: ピボット テーブルを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256658"
---
# <a name="how-to-use-the-pivottable"></a>ピボットテーブルの使用方法
ディメンションやビューを含む BAM ビューを定義した場合、そのビューに関連する 1 つ以上のピボットテーブルを更新する必要があります。  
  
 Excel のピボットテーブル レポートは、大量のデータを容易に組み合わせて比較できる対話型のテーブルです。 行や列の値は並べ替えることができ、表示されるデータを別のまとめ方で確認できます。 また、データに対して集計カウントや平均などの計算を実行できます。  
  
 ピボットテーブルを作成して使用するには、次の手順に従います。 ピボットテーブルの使用方法の詳細については、Microsoft Excel のドキュメントを参照してください。  
  
> [!NOTE]
>  リアルタイム集計のピボットテーブルを作成する場合は、最大 14 レベルのディメンションを含めることができます。  
  
> [!IMPORTANT]
>  Excel ワークシートで複数のピボットテーブルを定義すると、アクティビティから大きなデータセットが返された場合に、結果のテーブルが増大して重なり合う可能性があります。 このシナリオでは「ピボット テーブル レポートは、別のピボット テーブル レポートを重ねることはできません」が表示されます、データを更新するときにします。 このエラーを修正するには、テーブルが重なり合うことなく増大できるように、ピボットテーブル間に列または行を追加します。  
  
### <a name="to-use-the-pivottable"></a>ピボットテーブルを使用するには  
  
1.  ピボットテーブルで使用する BAM ビューを作成します。 BAM ビューの作成の詳細については、次を参照してください[ビジネス アクティビティ ビューの定義。](../core/defining-a-bam-view.md)  
  
2.  使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つ以上使用可能なディメンションをピボット テーブル テンプレートの行と列の領域にします。  
  
3.  使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つ以上使用できるメジャー データ項目の領域に、ピボット テーブル テンプレートのです。  
  
     ピボットテーブルを更新すると、サンプル データが追加されます。 このサンプル データを使用すると、ピボットテーブルの構成方法を判断できます。  
  
4.  使用して、**ピボット テーブル**ツールバーで、グラフ、ピボット テーブルと関連付けます。  
  
5.  Excel のブックを保存します。