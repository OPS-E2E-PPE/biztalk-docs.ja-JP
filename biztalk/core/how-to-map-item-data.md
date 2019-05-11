---
title: 項目のデータをマップする方法 |Microsoft Docs
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
ms.openlocfilehash: cc3e5c4c4d2ddd4b0051ef5c8b838a0882baa5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336597"
---
# <a name="how-to-map-item-data"></a>データ項目をマップする方法
オーケストレーションからのデータ抽出を定義する項目のデータをマップします。  
  
> [!NOTE]
>  必要がありますに追跡プロファイルを作成するときにアクティビティ項目と互換性のあるデータ型の値をマップします。 データ型に互換性がない場合、BAM ランタイム エラーが表示されます。  
  
> [!NOTE]
>  日付/時刻スタンプなどのマイルス トーンをマップするときマップされているデータは日付タイムスタンプの SQL の文字列形式に従う必要があります。 YYYY、次のように書式設定されている XML の DateTime 形式の DateTime データ-MM-DDTHH:MM:SS.mmm-HH:MM ではサポートされていません。  
>   
>  たとえば、次の日付文字列、1999-05-31T13:20:00.000-05時 00分はサポートされていません。  
  
## <a name="prerequisites"></a>前提条件  
 展開された BAM アクティビティ定義とオーケストレーションに接続します。  
  
### <a name="how-to-map-item-data"></a>項目のデータをマップする方法  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。  
  
2.  シナリオでは、LoanProcessBamDef というアクティビティ定義をインポートします。 含まれている、 **LoanProcess**アクティビティ ノードに、顧客の**SSN**が ActivityID として。 詳細については、次を参照してください。[アクティビティ ノードと ActivityID ノード](../core/activity-and-activityid-nodes.md)します。  
  
3.  すべてのアクティビティに、ActivityID または ContinuationID データ項目を追跡するために顧客の SSN などのことを確認します。  
  
4.  オーケストレーションのアクションを追跡するためにイベントを示すために、適切なビジネス イベント フォルダーにマップします。たとえば、ローン処理のシナリオでは、他のユーザーの間で、次の項目がドラッグ下、 **LoanProcess**アクティビティ フォルダー。  
  
    -   **LoanApplicationReceived**  
  
    -   **CreditHistoryRequest**  
  
    -   **CreditHistoryResponse**  
  
## <a name="see-also"></a>参照  
 [データ項目ノード](../core/data-item-nodes.md)   
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)