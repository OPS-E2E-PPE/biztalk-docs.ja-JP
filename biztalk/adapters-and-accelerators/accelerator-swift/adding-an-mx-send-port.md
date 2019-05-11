---
title: MX の送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878353f8082ba7990c6e15bc46876544b83e9508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378691"
---
# <a name="adding-an-mx-send-port"></a>MX 送信ポートを追加します。
**追加、MX 送信ポートを使用します。**  
  
1.  右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、名前で型をボックス**MX_SendPort**します。  
  
3.  [種類] ボックスに、トランスポート] セクションで、ドロップダウン リストをクリックし、[**ファイル**します。  
  
4.  をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  
  
6.  [参照] ダイアログ ボックスのフォルダーでは、ファイルの場所を選択します。  
  
7.  ファイル名 ボックスに、入力 **%MessageID%.xml**、 をクリックし、 **OK**します。  
  
8.  送信ポートのプロパティ ダイアログ ボックスでは、送信パイプライン ボックスで、ドロップダウン リストをクリックし、パイプライン プロジェクトを配置した送信パイプラインを選択します。  
  
9. 左側のウィンドウで次のようにクリックします。**フィルター**、し、次を指定します。  
  
    |||  
    |-|-|  
    |プロパティ|Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed|  
    |演算子|選択 = =|  
    |値|False|  
  
10. クリックして**適用**、順にクリックします**OK**します。  
  
11. 送信ポート ペインで右クリック**MX_SendPort**、 をクリックし、**開始**します。