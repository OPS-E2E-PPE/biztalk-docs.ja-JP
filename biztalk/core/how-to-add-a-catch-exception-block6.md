---
title: Catch の例外 Block6 を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: a84b37953e05c83beff6853cd7143c7db2a36036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387372"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 BizTalk server の多くとして割り当てることができます**例外のキャッチ**ブロックする必要があります。  
  
 さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。 各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する`System.Exception`します。 例外ブロックが、一般的な例外ハンドラーとして扱われから派生していない例外をキャッチできる例外の種類を指定しない場合`System.Exception`します。  
  
 例外ハンドラーで指定された型と一致する例外がスローされます、その例外ハンドラーが呼び出されます。 その他の例外がスローされた場合は、既定の例外ハンドラーによって処理されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロックを**スコープ**、図形、**トランザクションの種類**のプロパティ、**スコープ**図形はか長を None に設定する必要があります実行中です。  
  
## <a name="adding-and-populating-a-catch-exception-block"></a>追加と例外のキャッチ ブロックの設定  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a>追加して例外のキャッチ ブロックを設定するには  
  
1.  右クリックし、**スコープ**を追加する図形を**例外のキャッチ**、ブロックし、をクリックし、**新しい例外ハンドラー**します。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。  
  
2.  **プロパティ**ウィンドウで、プロパティを指定します。 最も重要なプロパティは、**例外オブジェクト型**キャッチするメッセージの種類です。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。|  
  
3.  **プロパティ**ウィンドウで、をクリックして、**例外オブジェクト型**一覧。 この一覧には、アダプターによってスローされる一般的な例外が含まれています。  
  
     名前は PS. など、バックエンド システムへのポートで設定したエラーとして表示されます。SQLExecute.Fault します。  
  
4.  名前を追加、**例外オブジェクト名**、たとえば、テストします。  
  
     内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。  
  
    1.  下を右クリック、**例外のキャッチ**、 をポイント**図形の挿入**、選び**メッセージの構築**します。  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。  
  
         設定した名前を入力、**例外オブジェクト名**から、**例外のキャッチ**、およびエラー用に作成した新しいメッセージ。  
  
         たとえば、「 `Message_3 = Test`」のように入力します。  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a>参照  
 [スコープ図形を追加する方法](../core/how-to-add-a-scope-shape1.md)   
 [例外完了メッセージ](../core/completing-the-exception-message3.md)   
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)