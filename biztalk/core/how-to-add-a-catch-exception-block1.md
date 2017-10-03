---
title: "Catch 例外 Block1 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7922a1527e0f6359427be992c4cc9963f8c7d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 数だけ接続できます**例外のキャッチ**ブロックする必要があります。  
  
 例外ハンドラーを設定すると、各種の例外を処理することができます。 各例外ハンドラーでは、例外の種類を指定します。例外またはクラス `System` から派生したオブジェクトのいずれかを指定する必要があります。 例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロック、**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>追加して、例外のキャッチ ブロックを設定するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは、キャッチするメッセージの種類を表す "例外オブジェクト名" です。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。|  
  
3.  **プロパティ**] ウィンドウで、**例外オブジェクト型**一覧で、[、**一般例外**です。  
  
4.  内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。  
  
5.  下を右クリックし、**例外のキャッチ**をブロックし、**図形の挿入**、し、**メッセージの構築**です。  
  
6.  内でダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化し、メッセージの割り当てを入力します。  
  
     たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message5.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape2.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)