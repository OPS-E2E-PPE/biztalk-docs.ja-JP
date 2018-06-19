---
title: ビジネス アクティビティを定義する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74cb0bb6f2bd0a5f92f6029dda65d55d219bcc12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249834"
---
# <a name="how-to-define-a-business-activity"></a>ビジネス アクティビティを定義する方法
レポート用に収集が必要なデータを指定するには、BAM アクティビティを定義する必要があります。 アクティビティには、BAM を使用して追跡する重要なマイルストーンとデータ項目の一覧を含めます。BAM Excel アドインを使用し、以下の手順に従ってアクティビティを作成します。  
  
> [!NOTE]
>  アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。 特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。 このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。  
  
### <a name="to-create-a-business-activity"></a>ビジネス アクティビティを作成するには  
  
1.  Microsoft Excel を開きます。  
  
2.  ツールバーのメニュー、をクリックして、 **BAM**メニュー項目をクリック**BAM アクティビティ**です。  
  
     **ビジネス アクティビティ監視アクティビティ ウィザード**が表示されます。  
  
3.  をクリックして**新しいアクティビティ**です。  
  
     **新しいアクティビティ** ダイアログ ボックスが表示されます。  
  
4.  アクティビティのわかりやすい名前を入力、**アクティビティ名**テキスト ボックス。  
  
> [!NOTE]
>  アクティビティには、少なくとも 1 つのアクティビティ項目が含まれている必要があります。  
  
#### <a name="to-create-a-new-item"></a>新しい項目を作成するには  
  
1.  をクリックして**新しい項目の**します。  
  
2.  **新しいアクティビティ項目** ダイアログ ボックスで、**新しいアクティビティ項目**ボックスに、わかりやすいアクティビティ項目の名前を入力します。  
  
3.  **項目の種類**ドロップダウン メニューでは、この項目の種類を選択します。 有効な値は次のとおりです。  
  
    |アイテムの種類|Description|  
    |---------------|-----------------|  
    |ビジネス マイルス トーン|日付/時刻値。 たとえば、注文書が承認された日付です。|  
    |ビジネス データ - テキスト|任意の英数字の文字列。 たとえば、出荷先 : 市区町村、都道府県、郵便番号です。|  
    |ビジネス データ-Integer|整数値です。 たとえば、注文の合計数です。|  
    |ビジネス データ - 10 進数|decimal 値です。 たとえば、PO の合計金額です。|  
  
     "ビジネス データ-Text"の型、アイテムを選択する場合は、文字列の最大文字数を入力する必要があります、**最大長**ボックス。  
  
    > [!NOTE]
    >  これらの項目の作成の詳細については、Microsoft BizTalk Server チュートリアルの「パートナーの管理とビジネス アクティビティの監視」を参照してください。  
  
4.  手順 1. ～ 3. を繰り返して、このアクティビティに必要な数だけ項目を追加します。  
  
5.  ビジネス アクティビティ監視アクティビティ ウィザードを完了すると、ビジネス アクティビティ監視ビュー ウィザードが自動的に開始されます。  
  
 詳細については、このウィザードを使用して、次を参照してください。 [BAM ビューを定義する](../core/defining-a-bam-view.md)です。  
  
## <a name="see-also"></a>参照  
 [BAM ビューを定義します。](../core/defining-a-bam-view.md)   
 [Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md)