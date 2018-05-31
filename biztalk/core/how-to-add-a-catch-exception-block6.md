---
title: Catch 例外 Block6 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248722"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 BizTalk Server では、数だけ接続できます**例外のキャッチ**ブロックする必要があります。  
  
 例外ハンドラーを設定すると、各種の例外を処理することができます。 各例外ハンドラでは、例外の種類を指定します。エラー メッセージまたはクラス `System.Exception` から派生したオブジェクトのいずれかを指定する必要があります。 例外の種類を指定しなかった場合、その例外ブロックは一般的な例外ハンドラとして扱われ、`System.Exception` からの派生ではない例外をキャッチする可能性があります。  
  
 例外ハンドラで指定した型に一致する例外がスローされると、該当する例外ハンドラが呼び出されます。 その他の型の例外がスローされた場合、その例外は既定の例外ハンドラによって処理されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**か長を None に図形を設定する必要があります実行中です。  
  
## <a name="adding-and-populating-a-catch-exception-block"></a>例外のキャッチ ブロックの追加と設定  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a>例外のキャッチ ブロックを追加して設定するには  
  
1.  右クリックし、**スコープ**を追加する図形、**例外のキャッチ**、ブロックし、をクリックして**新しい例外ハンドラー**です。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。 最も重要なプロパティは、**例外オブジェクト型**キャッチするメッセージの種類は、このためです。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。|  
  
3.  **プロパティ**ウィンドウで、をクリックして、**例外オブジェクト型** ボックスの一覧です。 この一覧には、アダプタによってスローされる一般的な例外が含まれています。  
  
     名前は、バックエンド システムへのポートで設定したエラーとして表示されます (たとえば PS.SQLExecute.Fault)。  
  
4.  名前を追加、**例外オブジェクト名**、たとえば、テストします。  
  
     内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。  
  
    1.  下を右クリックし、**例外のキャッチ**、 をポイント**図形の挿入**を選択して**メッセージの構築**です。  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  内でダブルクリックして**MessageAssignment**するテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         設定した名前を入力、**例外オブジェクト名**から、**例外のキャッチ**、およびエラー用に作成した新しいメッセージ。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a>参照  
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape1.md)   
 [例外完了メッセージ](../core/completing-the-exception-message3.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)