---
title: Catch 例外 block4 などを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 9cf27fd031f5887eed499eb1b10418fa911a127c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387365"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。  
  
 さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。 各例外ハンドラーでは、例外またはクラス System から派生したオブジェクトのいずれかにする必要があります例外の種類を指定します。 例外ハンドラーで指定された型と一致する例外がスローされます、その例外ハンドラーが呼び出されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロックを**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。  
  
|追加と例外のキャッチ ブロックの設定|  
|---------------------------------------------------|  
|1.右クリックし、**スコープ**を追加する図形を**例外のキャッチ**をブロックし、をクリックして**新しい例外ハンドラー**します。<br />     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。<br />2.**プロパティ**ウィンドウで、プロパティを指定します。 最も重要なは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。<br />     **例外オブジェクト名**<br />     -例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。<br />     **例外オブジェクト型**<br />     -(System.Exception から派生) オブジェクトの種類を決定します。 この例外ハンドラーでキャッチします。<br />3.**プロパティ**ウィンドウを開いて、**例外オブジェクト型**一覧。 このリストには、**一般例外**します。<br />4.内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。<br />5.下を右クリック、**例外のキャッチ**、 をポイント**図形の挿入**、選び**メッセージの構築**します。<br />6.中をダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化して、メッセージの割り当てを入力します。<br />     たとえば、メッセージ _ 3 で入力テストを = です。<br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message2.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape3.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)