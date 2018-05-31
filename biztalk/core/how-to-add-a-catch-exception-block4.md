---
title: Catch 例外 block4 などを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 632fa089-a1af-4126-b32b-68d4d8942387
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b409f25fc32c609bb4c1a80c0582cdb1c363e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246826"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 数だけ接続できます**例外のキャッチ**ブロックする必要があります。  
  
 例外ハンドラーを設定すると、各種の例外を処理することができます。 各例外ハンドラーでは、例外の種類を指定します。例外またはクラス System から派生したオブジェクトのいずれかを指定する必要があります。 例外ハンドラで指定した型に一致する例外がスローされると、該当する例外ハンドラが呼び出されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロック、**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。  
  
|追加して、例外のキャッチ ブロックを設定します。|  
|---------------------------------------------------|  
|1.右クリックし、**スコープ**を追加する図形、**例外のキャッチ**、ブロックし、をクリックして**新しい例外ハンドラー**です。<br />     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。<br />2.**プロパティ**ウィンドウで、プロパティを指定します。 最も重要なは、**例外オブジェクト型**です。 これは、キャッチするメッセージの種類。<br />     **例外オブジェクト名**<br />     -例外ハンドラーによってキャッチされた例外オブジェクトに名前を割り当てます。<br />     **例外オブジェクト型**<br />     -(System.Exception から派生) オブジェクトの種類を判別します。 この例外ハンドラーでキャッチします。<br />3.**プロパティ**ウィンドウを開いた、**例外オブジェクト型** ボックスの一覧です。 この一覧には、**一般例外**です。<br />4.内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。<br />5.下を右クリックし、**例外のキャッチ**、 をポイント**図形の挿入**を選択して**メッセージの構築**です。<br />6.内でダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化し、メッセージの割り当てを入力します。<br />     たとえば、「Message_3 = Test」と入力します。<br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message2.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape3.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)