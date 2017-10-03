---
title: "MX 送信ポートを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd4c16658ad0ff6b85976fbc6a97c4f397acbdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-an-mx-send-port"></a>MX 送信ポートを追加します。
**MX 送信ポートを追加します。**  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、名前で型をボックス**MX_SendPort**です。  
  
3.  トランスポート セクションで、種類 ボックスのドロップダウン リストをクリックし、選択**ファイル**です。  
  
4.  クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
6.  フォルダ ダイアログ ボックスの参照、ファイルの場所を選択します。  
  
7.  ファイル名 ボックスに入力**%MessageID%.xml**、順にクリック**OK**です。  
  
8.  送信ポートのプロパティ ダイアログ ボックスでは、送信パイプライン ボックスで、ドロップダウン リストをクリックし、パイプライン プロジェクトで展開して、送信パイプラインを選択します。  
  
9. 左側のウィンドウでをクリックして**フィルター**、次を指定します。  
  
    |||  
    |-|-|  
    |プロパティ|Microsoft.Solutions.MX_A4SWIFT です。Property.MX_A4SWIFT_Failed|  
    |演算子|オン = =|  
    |値|False|  
  
10. をクリックして**適用**、順にクリック**OK**です。  
  
11. 送信ポート ペインで右クリック**MX_SendPort**、クリックして**開始**です。