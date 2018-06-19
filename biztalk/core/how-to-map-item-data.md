---
title: 項目のデータをマップする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253954"
---
# <a name="how-to-map-item-data"></a>データ項目をマップする方法
データ項目をマップして、オーケストレーションからのデータ抽出を定義します。  
  
> [!NOTE]
>  追跡プロファイルを作成する際には、マップする値がアクティビティ項目と互換性のあるデータ型の値であることを確認する必要があります。 データ型に互換性がないと、BAM 実行時エラーが表示されます。  
  
> [!NOTE]
>  日付時刻スタンプなど、マイルストーンをマップする際、マップするデータは日付時刻スタンプを表す SQL 文字列表記に準拠している必要があります。 YYYY-MM-DDTHH:MM:SS.mmm-HH:MM という XML の DateTime 形式で表記された DateTime データはサポートされません。  
>   
>  たとえば、1999-05-31T13:20:00.000-05:00 という日付文字列はサポートされません。  
  
## <a name="prerequisites"></a>前提条件  
 BAM アクティビティ定義と、接続先のオーケストレーションを展開しておく必要があります。  
  
### <a name="how-to-map-item-data"></a>項目のデータをマップする方法  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。  
  
2.  このシナリオでは、LoanProcessBamDef という名前のアクティビティ定義をインポートします。 含まれている、 **LoanProcess**アクティビティ ノードには、お客様の**SSN**が ActivityID として。 詳細については、次を参照してください。[アクティビティ ノードと ActivityID ノード](../core/activity-and-activityid-nodes.md)です。  
  
3.  すべてのアクティビティに、顧客の SSN など、追跡する ActivityID データ項目または ContinuationID データ項目があることを確認します。  
  
4.  オーケストレーションのアクションを適切な Business Events フォルダーにマップして、追跡するイベントを示します。たとえば、ローン処理のシナリオでは、他のユーザー間で、次の項目はドロップ下にある、 **LoanProcess**アクティビティ フォルダー。  
  
    -   **LoanApplicationReceived**  
  
    -   **CreditHistoryRequest**  
  
    -   **CreditHistoryResponse**  
  
## <a name="see-also"></a>参照  
 [データ項目ノード](../core/data-item-nodes.md)   
 [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)