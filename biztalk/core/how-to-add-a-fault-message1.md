---
title: "フォールト Message1 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a>エラー メッセージを追加する方法
最初に作成したバックエンド システムへのポートには、要求と応答が含まれていました。 例外を取得するには、これにエラーを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1.  右クリック**ポート操作**、クリックして、**新しいエラー メッセージ**です。  
  
     A**フォールト**下に表示されます、**要求と応答**ポートです。  
  
2.  **オーケストレーション**画面を右クリックして**メッセージ**、し、**新しいメッセージ**です。  
  
     これにより Message_3 が作成され、このエラーに割り当てることができます。  
  
3.  右クリック**Message_3**にアクセスする、**プロパティ**ウィンドウです。  
  
    1.  設定、**メッセージの種類**です。  
  
    2.  選択**スキーマ**から順に選択および**ref アセンブリ**です。  
  
         開き、**成果物の種類の選択**ウィンドウです。  
  
    3.  画面をスクロールし、完全修飾エラーを選択します。  
  
         名前は**BTS です。SOAP_Envelope_1__1.fault**です。 をクリックして**OK**選択を確定し、ウィンドウを閉じます。  
  
4.  右クリックし、**フォールト**にアクセスする、**プロパティ**ウィンドウです。  
  
    1.  設定、**メッセージの種類**です。  
  
    2.  選択**スキーマ**から順に選択および**ref**アセンブリ。  
  
         開き、**成果物の種類の選択**ウィンドウです。  
  
    3.  画面をスクロールし、完全修飾エラーを選択します。  
  
         名前は**BTS です。SOAP_Envelope_1__1.fault**です。  
  
    4.  をクリックして**OK**選択を確定し、ウィンドウを閉じます。  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  エラーに名前を付けたら、この名前を CatchException の例外オブジェクト型に設定します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)