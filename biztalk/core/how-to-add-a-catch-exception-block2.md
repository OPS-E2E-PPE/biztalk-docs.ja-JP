---
title: Catch の例外 Block2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e16fb42f9b8814ab816f64f6cf2b3a8b482fbb58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387416"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。  
  
 さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。 各例外ハンドラーでは、例外の種類を指定します。 例外またはクラスから派生したオブジェクトのいずれかにあるこの必要があります`System`します。 例外がスローされた例外ハンドラーで指定された型と一致する場合は、その例外ハンドラーが呼び出されます。  
  
> [!NOTE]
>  例外のキャッチ ブロックをスコープ図形を追加するにスコープ図形のトランザクションの種類のプロパティを設定**None**または**長時間**します。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>追加して、例外のキャッチ ブロックを設定するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**ブロックし、クリックして**新しい例外ハンドラー**します。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。  
  
3.  **プロパティ**windows で、**例外オブジェクト型**一覧で、**一般例外**します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |**例外オブジェクト名**|例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。|  
    |**例外オブジェクト型**|オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。|  
  
4.  例外のキャッチ ブロック内では、例外を処理するプロセスを作成する図形を追加します。  
  
    1.  下を右クリック、 **CatchException** ] をポイント**図形の挿入**、し、[**メッセージの構築**します。  
  
    2.  中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message4.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape4.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)