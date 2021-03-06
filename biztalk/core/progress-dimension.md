---
title: 進捗ディメンション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], progress dimensions
- Progress dimension [BAM]
ms.assetid: 472fcbf6-502f-4c81-bf48-f7eec98e391b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf49090260b2765620e3b968ee5dd3e70f4c2d01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395625"
---
# <a name="progress-dimension"></a>進捗ディメンション
到達したマイルス トーンで BAM アクティビティをグループ化の進行状況ディメンションを使用します。 これは最適な例を示します。  
  
 チュートリアル 1 のアイテムの要求を処理するオーケストレーションを検討してください。 (を参照してください[チュートリアル 1。エンタープライズ アプリケーション統合](../core/tutorial-1-enterprise-application-integration.md)このオーケストレーションの詳細についてはします)。オーケストレーションには、判断図形と 2 つの分岐が含まれています。 [チュートリアル 4。ビジネス アクティビティ監視](http://msdn.microsoft.com/library/81d5e768-f8a6-4eb0-8e6c-64db47455476)ビジネス マイルス トーン Denied を拒否する要求を表す分岐内の図形にマップして、ビジネス マイルス トーン Approved を承認要求を表す分岐内の図形にマップします。 ビジネス マイルス トーン Approved および Denied を含む進捗ディメンションを作成します。 進捗ディメンションをピボット テーブルを使用する場合は、かどうかを承認または拒否されたでグループ化された BAM アクティビティを表示できます。 これは、次の図に示します。  
  
 ![Approved および Denied の列を含むピボット テーブル](../core/media/bts-view-with-approved-denieds.gif "列-と-承認-denieds")  
  
 これは、チュートリアルでは実行されませんが、内、Denied マイルス トーンを定義できます。 たとえば、オーケストレーションは、拒否の理由が特定された場合、は、サブのマイルス トーン Denied マイルス トーン内で Poor credit および在庫切れをという名前を作成できます。 ピボット テーブルで、進捗ディメンションを使用した場合は、Poor credit マイルス トーンに到達した BAM アクティビティと在庫のマイルス トーンに到達した BAM アクティビティを表示する、Denied マイルス トーンにドリルダウンする可能性があります。  
  
 BAM の進行状況ディメンションから成る*マイルス トーンが進捗状況*と*ステージの進行状況*します。 進捗マイルス トーンでは、分類、BAM アクティビティをグループ化方法を表します。 Approved し、Denied に承認または拒否された要求のアクティビティを分類するため、たとえばは進捗マイルス トーンです。  
  
> [!NOTE]
>  2 つの概念の「マイルス トーン」という単語の使用は、残念ではありません。 A*ビジネス マイルス トーン*BAM アクティビティ内のアクティビティ アイテムは、アプリケーションで何らかのイベントが発生した日時を表します。 A*進捗マイルス トーン*はアクティビティ インスタンスをグループ化する方法です。 各進捗マイルス トーンは、ビジネス マイルス トーンに対応します。 混乱を最小限に抑えるには、進捗マイルス トーンとそれに対応するビジネス マイルス トーンに同じ名前の使用を検討します。  
  
 進捗段階は、同等のマイルス トーンのグループです。 サブ マイルス トーンには、この例には、2 つの進捗段階が含まれています。 最初の進捗段階は、進捗マイルス トーン Approved および Denied で構成されます。 2 番目の進捗段階は、Poor credit および在庫の 進捗マイルス トーンで構成されます。  
  
 進捗ディメンションは、進捗マイルス トーンのルートとして始まります。 この進捗マイルス トーンは、多くの場合、受信元のメッセージを表します。 各進捗マイルス トーンは、1 つの進捗段階とその他の進捗マイルス トーンの任意の数に含めることができます。 進捗段階内のすべての進捗マイルス トーンは、相互に排他的である必要があります。 次の図では、Disposition および Reason に、進捗段階は、一方、Received、Approved、Denied、役に立たなかった貸方、および out of stock が進捗マイルス トーン。  
  
 ![2 を定義する&#45;レベルの進捗ディメンション](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress ディメンションの 2 つ levelss")  
  
## <a name="how-to-create-progress-dimensions"></a>進捗ディメンションを作成する方法  
 作成時に、BAM ビュー ウィザードを使用する前に、進捗ディメンションをデザインします。 次の表は、進捗ディメンションを設計するためのプロセスを識別し、各手順の例を示します。  
  
|[処理]|例|  
|-------------|-------------|  
|カテゴリとレポートするサブカテゴリの階層を描画します。<br /><br /> これらのレベルは、進捗マイルス トーンになります。|受信。<br /><br /> 承認済み<br /><br /> 拒否<br /><br /> -Poor Credit<br /><br /> -Out Of Stock|  
|同じレベルのカテゴリのセットごとに、それらのカテゴリを表す名前を選択します。<br /><br /> このセットの名前には、進捗段階になります。|Approved および Denied を含むレベルを"disposition"と呼びます。<br /><br /> Poor Credit および Out Of Stock を含むレベルを"reason"と呼びます。|  
|各進捗マイルス トーンを表すビジネス マイルス トーンを識別します。<br /><br /> **注:** BAM アクティビティは、これらのビジネス マイルス トーンのそれぞれのアクティビティ項目を含める必要があります。|受信。受信しました。<br /><br /> 承認。承認<br /><br /> 拒否。拒否<br /><br /> Poor Credit:拒否 poor credit<br /><br /> Out of Stock:拒否-の在庫切れ|  
  
 進捗ディメンションを作成するときに、これらの進捗マイルス トーン、ステージ、およびビジネス マイルス トーンを使います。  
  
> [!NOTE]
>  ディメンションを作成する時点で、次の手順を開始します。 既にが BAM アクティビティを作成して BAM ビューの作成を開始します。  
  
#### <a name="to-create-a-progress-dimension"></a>進捗ディメンションを作成するには  
  
1.  をクリックして、**アドイン**、タブを選び**BAM ビュー**から、 **BAM**ドロップダウン リストで、**メニュー コマンド**グループ。  
  
2.  BAM ビュー ウィザードで次のようにクリックします。**次**が表示されるまで、**新しい BAM ビュー。集計ディメンションおよび集計メジャー**ページ。  
  
3.  クリックして**新しいディメンション**します。  
  
4.  **新しいディメンション**ダイアログ ボックスで、ディメンションの名前を入力、**ディメンション名**ボックスを選び**進捗ディメンション**から、**ディメンション型**ドロップダウン リスト。  
  
5.  クリックして**新しいマイルス トーン**します。  
  
6.  **進捗マイルス トーン**のボックス、**新しい進捗マイルス トーン** ダイアログ ボックスに、デザインした階層の最上位レベルにある進捗マイルス トーンの名前を入力します。 実行中の例では、入力`Received`します。  
  
7.  進捗マイルス トーンに対応するビジネス マイルス トーンを選択し、クリックして**OK**します。 実行中の例では、選択**Received (\<アクティビティ名\>)** します。  
  
8.  **新しいディメンション**ダイアログ ボックスで、をクリックして**新しいステージ**します。  
  
9. **ステージの進行状況**のボックス、**新しい進捗段階**ダイアログ ボックスで、最上位レベルのステージの名前を入力し、順にクリックします**OK**します。  実行中の例では、入力**廃棄**します。  
  
10. **新しいディメンション**ダイアログ ボックスで、をクリックして**新しいマイルス トーン**します。  
  
11. **進捗マイルス トーン**のボックス、**新しい進捗マイルス トーン** ダイアログ ボックスに、最初のレベルのマイルス トーンの 1 つの名前を入力します。 入力を使用している例では、`Approved`します。  
  
12. **ビジネス マイルス トーン**ドロップダウン ボックスが進捗マイルス トーンに対応するビジネス マイルス トーンを選択し、クリックして**OK**します。 実行中の例では、選択**Approved (\<アクティビティ名\>)** します。  
  
13. 同じ進捗段階内の他のマイルス トーンを追加する前の 3 つの手順を繰り返します。  
  
14. ビジネス マイルス トーンにサブ マイルス トーンが含まれている場合は、親のマイルス トーンを選択、**新しいディメンション**ダイアログ ボックスで、をクリックして**新しいステージ**、サブ段階を定義する 5 つ前の手順を繰り返しますとそのマイルス トーンです。  
  
     次に示します、**新しいディメンション** ダイアログ ボックスの例の進捗ディメンションを作成した後。  
  
     ![2 を定義する&#45;レベルの進捗ディメンション](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress ディメンションの 2 つ levelss")  
  
## <a name="see-also"></a>参照  
 [Excel でビジネス アクティビティとビューの定義](../core/defining-business-activities-and-views-in-excel.md)   
 [データ ディメンション](../core/data-dimension.md)   
 [時間ディメンション](../core/time-dimension.md)   
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)