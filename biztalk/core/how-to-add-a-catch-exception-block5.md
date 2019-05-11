---
title: Catch の例外 Block5 を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 60e2674823ff92b1ffe59a304b8cbe766c8e7e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343943"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。  
  
### <a name="to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形をクリックして**新しい例外ハンドラー**します。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。  
  
     最も重要なプロパティは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |**例外オブジェクト名**|例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。|  
    |**例外オブジェクト型**|オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。|  
  
3.  **プロパティ**ウィンドウで、**例外オブジェクト型**一覧で、**一般例外**します。  
  
4.  内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。  
  
    1.  下を右クリック、 **CatchException** ] をポイント**図形の挿入**、し、[**メッセージの構築**します。  
  
    2.  中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
## <a name="see-also"></a>参照  
 [例外完了メッセージ](../core/completing-the-exception-message1.md)   
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape5.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling5.md)