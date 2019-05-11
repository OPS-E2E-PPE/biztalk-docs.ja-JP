---
title: Catch の例外 Block1 を追加する方法 |Microsoft Docs
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
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34e5ebf17db715175a532f0ec0863a506b9e3557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344008"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。  
  
 さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。 各例外ハンドラーで例外またはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する`System`します。 例外がスローされた例外ハンドラーで指定された型と一致する場合は、その例外ハンドラーが呼び出されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロックを**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>追加して、例外のキャッチ ブロックを設定するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**ブロックし、クリックして**新しい例外ハンドラー**します。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは例外オブジェクト型です。これは、キャッチするメッセージの種類です。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。|  
  
3.  **プロパティ**ウィンドウで、**例外オブジェクト型**一覧で、、**一般例外**します。  
  
4.  内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。  
  
5.  下を右クリック、**例外のキャッチ**ブロックをポイントして、**図形の挿入**、し、**メッセージの構築**します。  
  
6.  中をダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化して、メッセージの割り当てを入力します。  
  
     たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message5.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape2.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)