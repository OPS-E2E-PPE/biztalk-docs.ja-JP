---
title: "JD Edwards OneWorld 用送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>JD Edwards OneWorld 用送信ポートの作成方法
次の手順を使用すると、送信ポートを作成できます。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**に移動し、必要なアプリケーションです。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
    > [!NOTE]
    >  使用することも**静的な一方向ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドで、送信ポートの名前を入力 (たとえば、入力**SendToJDE**)。  
  
4.  **型**ドロップダウン リストで、 **[jdeoneworld]**です。  
  
5.  **URI**ドロップダウン リストで、送信ハンドラーを選択します。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld 送信ハンドラーの作成](../core/creating-jd-edwards-oneworld-send-handlers.md)