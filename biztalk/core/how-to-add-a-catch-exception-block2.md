---
title: "Catch 例外 Block2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e48ce1e6f0646acdf63ed33582f382f1baed797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 数だけ接続できます**例外のキャッチ**ブロックする必要があります。  
  
 例外ハンドラーを設定すると、各種の例外を処理することができます。 各例外ハンドラーでは、例外の種類を指定します。 これには、例外またはクラス `System` から派生したオブジェクトのいずれかを指定する必要があります。 例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。  
  
> [!NOTE]
>  スコープ図形には、例外のキャッチ ブロックを追加するには、スコープ図形のトランザクションの種類プロパティに設定する必要があります**None**または**長時間**です。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>追加して、例外のキャッチ ブロックを設定するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは、**例外オブジェクト型**です。 これは、キャッチするメッセージの種類。  
  
3.  **プロパティ**windows で、**例外オブジェクト型**一覧で、**一般例外**です。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |**例外オブジェクト名**|例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。|  
    |**例外オブジェクト型**|この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。|  
  
4.  例外のキャッチ ブロックの内側で、図形を追加して、例外を処理するためのプロセスを作成します。  
  
    1.  下を右クリックし、 **CatchException**を指す**図形の挿入**、し、**メッセージの構築**です。  
  
    2.  内でダブルクリックして**MessageAssignment**するテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message4.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape4.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)