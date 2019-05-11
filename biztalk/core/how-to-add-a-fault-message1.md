---
title: フォールト Message1 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9bcaab8db10ee0be664b02028af9b9a79981d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343845"
---
# <a name="how-to-add-a-fault-message"></a>エラー メッセージを追加する方法
最初に、バックエンド システムへのポートを作成したときに、要求と応答が含まれています。 例外をキャプチャするエラーを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1.  右クリック**ポート操作**を選び、**新しいエラー メッセージ**します。  
  
     A**フォールト**下に表示されます、**要求と応答**ポート。  
  
2.  **オーケストレーション**画面を右クリックして**メッセージ**、し、**新しいメッセージ**。  
  
     これには、エラーに割り当てることができる Message_3 が作成されます。  
  
3.  右クリックして**Message_3**にアクセスする、**プロパティ**ウィンドウ。  
  
    1.  設定、**メッセージの種類**します。  
  
    2.  選択**スキーマ**から選び**ref アセンブリ**します。  
  
         開き、**成果物の種類の選択**ウィンドウ。  
  
    3.  下へスクロールし、完全修飾エラーを選択します。  
  
         名前は**BTS します。SOAP_Envelope_1__1.fault**します。 クリックして**OK**選択を確定し、ウィンドウを閉じます。  
  
4.  右クリックし、**フォールト**にアクセスする、**プロパティ**ウィンドウ。  
  
    1.  設定、**メッセージの種類**します。  
  
    2.  選択**スキーマ**から選び**ref**アセンブリ。  
  
         開き、**成果物の種類の選択**ウィンドウ。  
  
    3.  下へスクロールし、完全修飾エラーを選択します。  
  
         名前は**BTS します。SOAP_Envelope_1__1.fault**します。  
  
    4.  クリックして**OK**選択を確定し、ウィンドウを閉じます。  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  エラーの名前を付けた後 CatchException の例外オブジェクト型にこの名前を設定します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)