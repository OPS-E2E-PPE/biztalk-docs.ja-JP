---
title: Catch 例外 Block5 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c045677fb2d177377725a3f11e81a5c5c70f9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246506"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクション タイプ**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。  
  
### <a name="to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形をクリックして**新しい例外ハンドラー**です。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは、**例外オブジェクト型**です。 これは、キャッチするメッセージの種類。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |**例外オブジェクト名**|例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。|  
    |**例外オブジェクト型**|この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。|  
  
3.  **プロパティ**] ウィンドウで、**例外オブジェクト型**一覧で、[**一般例外**です。  
  
4.  内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。  
  
    1.  下を右クリックし、 **CatchException**を指す**図形の挿入**、し、**メッセージの構築**です。  
  
    2.  内でダブルクリックして**MessageAssignment**するテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message1.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape5.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling5.md)